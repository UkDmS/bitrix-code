# фрагменты кода Bitrix
1. получаем параметры товара по PRODUCT_XML_ID<br>
$ar_res = CCatalogProduct::GetByIDEx($arItem['PRODUCT_XML_ID']);

$prop=CIBlockElement::GetByID($arResult["ORIGINAL_PARAMETERS"]['ID'])->GetNextElement()->GetProperties();
print "<pre>"; print_r($prop["do_not_forget"]["VALUE"]); print "</pre>";


$ID = array();
    $res = CIBlockElement::GetProperty(27,
    $GLOBALS['CATALOG_CURRENT_ELEMENT_ID'], "sort", "asc", array("CODE" => "do_not_forget"));
    while ($ob = $res->GetNext())
    {
        $ID[] = $ob['VALUE'];
    }
    global $arFilter;
$arFilter = array(
"ID" => $ID
            );
$APPLICATION->IncludeComponent(
				"bitrix:catalog.section",
				"do_not_forget",
				array(
					"IBLOCK_TYPE" => "fortis_content",
					"IBLOCK_ID" => "27",
					"SECTION_ID" => $arResult["IBLOCK_SECTION_ID"],
					"ID" => $GLOBALS['CATALOG_CURRENT_ELEMENT_ID'],
                    "SECTION_CODE" => "",
					"SECTION_USER_FIELDS" => array(
						0 => "",
						1 => "",
					),
                	"ELEMENT_SORT_FIELD" => "RAND",
					"ELEMENT_SORT_ORDER" => "RAND",
					"ELEMENT_SORT_FIELD2" => "RAND",
					"ELEMENT_SORT_ORDER2" => "RAND",
					"FILTER_NAME" => "arFilter",
					"INCLUDE_SUBSECTIONS" => "A",
					"SHOW_ALL_WO_SECTION" => "N",
					"HIDE_NOT_AVAILABLE" => "L",
					"PAGE_ELEMENT_COUNT" => "6",
					"LINE_ELEMENT_COUNT" => "5",
                    "PROPERTY_CODE" => array(
						0 => "BRAND",
						1 => "OFFERS",
						2 => "NEW_PRICE",
						3 => "",
					),
                    "OFFERS_LIMIT" => "5",
					"ADD_PICT_PROP" => "MORE_PHOTO",
					"LABEL_PROP" => array(
						0 => "do_not_forget",
					),
					"PRODUCT_SUBSCRIPTION" => "N",
					"SHOW_DISCOUNT_PERCENT" => "N",
					"SHOW_OLD_PRICE" => "N",
					"MESS_BTN_BUY" => "Купить",
					"MESS_BTN_ADD_TO_BASKET" => "В корзину",
					"MESS_BTN_SUBSCRIBE" => "Подписаться",
					"MESS_BTN_DETAIL" => "Подробнее",
					"MESS_NOT_AVAILABLE" => "Нет в наличии",
					"SECTION_URL" => "/catalog/#SECTION_CODE_PATH#/",
					"DETAIL_URL" => "/catalog/#SECTION_CODE_PATH#/#ELEMENT_CODE#/",
					"BASKET_URL" => "/personal/cart/",
					"ACTION_VARIABLE" => "action",
					"PRODUCT_ID_VARIABLE" => "id",
					"PRODUCT_QUANTITY_VARIABLE" => "quantity",
					"PRODUCT_PROPS_VARIABLE" => "prop",
					"SECTION_ID_VARIABLE" => "SECTION_ID",
					"AJAX_MODE" => "N",
					"AJAX_OPTION_JUMP" => "N",
					"AJAX_OPTION_STYLE" => "Y",
					"AJAX_OPTION_HISTORY" => "N",
					"CACHE_TYPE" => "A",
					"CACHE_TIME" => "36000000",
					"CACHE_GROUPS" => "Y",
					"META_KEYWORDS" => "-",
					"META_DESCRIPTION" => "-",
					"BROWSER_TITLE" => "-",
					"ADD_SECTIONS_CHAIN" => "N",
					"DISPLAY_COMPARE" => "N",
					"SET_TITLE" => "Y",
					"SET_STATUS_404" => "N",
					"CACHE_FILTER" => "N",
					"PRICE_CODE" => array(
						0 => "retail",
					),
					"USE_PRICE_COUNT" => "N",
					"SHOW_PRICE_COUNT" => "1",
					"PRICE_VAT_INCLUDE" => "Y",
					"PRODUCT_PROPERTIES" => array(
					),
					"USE_PRODUCT_QUANTITY" => "N",
					"CONVERT_CURRENCY" => "Y",
					"PAGER_TEMPLATE" => ".default",
					"DISPLAY_TOP_PAGER" => "N",
					"DISPLAY_BOTTOM_PAGER" => "N",
					"PAGER_TITLE" => "С этим товаром смотрят",
					"PAGER_SHOW_ALWAYS" => "N",
					"PAGER_DESC_NUMBERING" => "N",
					"PAGER_DESC_NUMBERING_CACHE_TIME" => "36000",
					"PAGER_SHOW_ALL" => "N",
					"AJAX_OPTION_ADDITIONAL" => "",
					"COMPONENT_TEMPLATE" => "default-new",
					"HIDE_NOT_AVAILABLE_OFFERS" => "Y",
					"BACKGROUND_IMAGE" => "-",
					"TEMPLATE_THEME" => "blue",
					"SHOW_MAX_QUANTITY" => "N",
					"SHOW_CLOSE_POPUP" => "N",
					"RCM_TYPE" => "similar",
					"RCM_PROD_ID" => $_REQUEST["PRODUCT_ID"],
					"SHOW_FROM_SECTION" => "Y",
					"SEF_MODE" => "N",
					"SET_BROWSER_TITLE" => "Y",
					"SET_META_KEYWORDS" => "Y",
					"SET_META_DESCRIPTION" => "Y",
					"SET_LAST_MODIFIED" => "N",
					"USE_MAIN_ELEMENT_SECTION" => "N",
					"COMPOSITE_FRAME_MODE" => "A",
					"COMPOSITE_FRAME_TYPE" => "AUTO",
					"CURRENCY_ID" => "RUB",
					"ADD_PROPERTIES_TO_BASKET" => "Y",
					"PARTIAL_PRODUCT_PROPERTIES" => "Y",
					"ADD_TO_BASKET_ACTION" => "ADD",
					"PAGER_BASE_LINK_ENABLE" => "N",
					"LAZY_LOAD" => "N",
					"LOAD_ON_SCROLL" => "N",
					"SHOW_404" => "N",
					"MESSAGE_404" => "",
					"COMPATIBLE_MODE" => "Y",
					"DISABLE_INIT_JS_IN_COMPONENT" => "N",
					"USE_ENHANCED_ECOMMERCE" => "N",
					"CUSTOM_FILTER" => "{\"CLASS_ID\":\"CondGroup\",\"DATA\":{\"All\":\"AND\",\"True\":\"True\"},\"CHILDREN\":[{\"CLASS_ID\":\"CondIBProp:27:174\",\"DATA\":{\"logic\":\"Great\",\"value\":0}}]}",
					"PROPERTY_CODE_MOBILE" => array(
						0 => "BRAND",
						1 => "NEW_PRICE",
					),
					"PRODUCT_ROW_VARIANTS" => "[{'VARIANT':'6','BIG_DATA':false}]",
            		"ENLARGE_PRODUCT" => "STRICT",
					"PRODUCT_BLOCKS_ORDER" => "price,props,sku,quantityLimit,quantity,buttons,compare",
					"SHOW_SLIDER" => "Y",
					"SLIDER_INTERVAL" => "3000",
					"SLIDER_PROGRESS" => "N",
					"LABEL_PROP_MOBILE" => array(
					),
					"LABEL_PROP_POSITION" => "top-left"
				),
				false
			);
