---
title: SKAN recommendations
excerpt: Use SKAN recommendations to optimize your conversion value settings and receive more accurate post-install activity measurements.
---

> **At a glance**: Use SKAN recommendations to optimize your conversion value settings and receive more accurate post-install activity measurements.

## Overview

SKAdNetwork (SKAN), part of Apple iOS, lets advertisers measure campaign performance while simultaneously preserving user privacy. With SKAdNetwork, post-install activity is measured using only numbers—conversions values— between 0-63.

The AppsFlyer <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Conversion Studio</Anchor> provides you with maximum flexibility to make every conversion value (CV) count. You determine precisely what measurement data should be encoded within the CV—including what activities should be measured during the post-install period, and for how long.

However, given the limited measurement capabilities of SKAN, it can be difficult to decide what to measure (for example, revenue, in-app events, or retention) and how to best utilize the CVs between 0-63. Decisions may be based on estimates, trial and error, or machine learning tools that use internal app data. And the measurements are not always as accurate as they could be.

AppsFlyer SKAN recommendations:

* Gives suggestions to improve your current CV settings and enhance your CV efficiency and measurement accuracy.
* Solves the difficulties you may have in making CV settings decisions.
* Are based on your specific vertical, geo, SKAN and non-SKAN app data, and user behavior.

## Recommendations

<div id="revenue" />

<Accordion title="Revenue">

#### **Understanding revenue recommendations**

Having the right revenue configuration schema is crucial to getting accurate revenue reporting.

The conversion value (CV) configuration you have to report revenue isn't necessarily 100% accurate, and SKAN-reported revenue may differ from actual revenue. For example, the actual (AF reported) ARPPU may be $10, but your current CV configuration reports SKAN ARPPU of $7, meaning SKAN underreports revenue for each paying user by $3.

AppsFlyer checks your non-SKAN revenue data (which is 100% accurate) on a daily basis, to make customized recommendations you can implement to improve the accuracy of your SKAN revenue reporting. The recommendations are also based on your saved activity window configuration in Conversion Studio, as well as your specific vertical, geo, and app user behavior.

The recommendations:

* Give you a clear picture of campaign performance with accurate revenue reporting.
* Save conversion values by using fewer ranges to accurately measure revenue.
* Take into account both in-app purchases and ad revenue.

#### **Revenue recommendations layout**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>Activity window as saved in your Conversion Studio configuration, during which SKAN revenue is measured.</span></td></tr><tr><td><p><span>B</span></p></td><td><span>Actual app average revenue per paying user (ARPPU) based on precise data from organic and non-organic users attributed via AppsFlyer (AF) methods.</span></td></tr><tr><td><p><span>C</span></p></td><td><p><span>Current configuration ARPPU (SKAN ARPPU), meaning the ARPPU measured <span>based on your current configuration in Conversion Studio for activity window and CV configuration for revenue reporting.</span></span></p></td></tr><tr><td><span>D</span></td><td><p><span>Estimated ARPPU: The expected ARPPU for your selected number of ranges. Calculated by taking all revenue data from the last 14 days for the app regardless of the attribution method (such as SKAN or classic method), divided by the number of paying users. </span><span>See F and G</span></p><p><span><strong>Note:</strong> </span><span>It is important to highlight that this number is not available in other AF dashboards. Here, we show the ARPPU (average revenue per paying user), while in other dashboards, we present the ARPU (average revenue per user).</span></p></td></tr><tr><td><p><span>E</span></p></td><td><p>Approximate error: The d<span>ifference between B and C. This can be a positive or negative error, depending on whether your SKAN ARPPU is overreported or underreported.</span></p><p><span>Example: If actual ARPPU is $10 and SKAN ARPPU is $7, the approximate error is an underreporting of 30% (-$3 dollars per user).</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>Recommendations for your SKAN revenue configuration. Select the number of ranges you want to include in your configuration.</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>Your current revenue configuration as set in Conversion Studio.</span><span></span></p></td></tr></tbody></table>

#### **Using revenue recommendations**

**Prerequisite:** Revenue recommendations require at least 14 days of revenue data.

> 📘 **Note**
>
> This is updated every day. Meaning that the recommendation period of 14 days back is from yesterday. For example: if today is August 28th. The input data for the recommendation is from August 13 to August 27.

**To use revenue recommendations:**

1. In AppsFlyer, depending on whether you use SKAN 4, custom or fixed mode [legacy], go to either:
   * **Settings** > **SKAN Conversion Studio** > **SKAN 4**> **Overall revenue/In-app event**.
   * **Settings** > **SKAN Conversion Studio** > **Custom** > **Overall revenue/In-app event**.
   * **Settings** > **SKAN Conversion Studio** > **Revenue**.
2. If you already have a revenue range configured, skip this step. If you don't have a revenue range configured, configure it now.  
   When the revenue range is configured, information about your configuration accuracy and approximate error displays.
3. Click **Check recommendations**.  
   Information about your current configuration displays, along with the revenue range recommendations and the estimated accuracy (approximate error) they will provide if implemented. Recommendations are provided for both keeping and changing the number of ranges.
4. Select a range recommendation.
5. Click **Apply recommendation**.
   * If you have your revenue configuration set in custom mode, the recommendation is applied.
   * If you have your revenue configuration in fixed mode (revenue), you need record the range recommendation, go to **SKAN Conversion Studio** > **Custom** > **Overall revenue**, and configure the recommended range.
6. Click **Save**.
   * If you then change anything in your revenue configuration, you can recheck your configuration and view new recommendations.

</Accordion>

<div data-zendesk-anchors="h_01HGSZ05CH4P8BQT23VYH6DKVP=overview h_01HGSZ05CHPZKWKY7MR6MA68YZ=recommendations h_01HGSZ05CH2RG3514N576ZGDFM=revenue h_01HGSZ05CHC93SHP28DN9EK27N=understanding-revenue-recommendations h_01HGSZ05CH5DVKAQ24EED16JRN=revenue-recommendations-layout h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=using-revenue-recommendations h_01HGSZCYCWRYEJPWZKDBC9SX8H=note" />
