---
title: Managing global thresholds
description: Use the procedures to set up hard and soft thresholds when working with global thresholds in the Back Office.
last_updated: Aug 9, 2021
template: back-office-user-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/managing-global-thresholds
originalArticleId: 99d7ee06-12fa-479a-a148-7728467fb950
redirect_from:
  - /2021080/docs/managing-global-thresholds
  - /2021080/docs/en/managing-global-thresholds
  - /docs/managing-global-thresholds
  - /docs/en/managing-global-thresholds
  - /docs/scos/user/back-office-user-guides/202200.0/administration/thresholds/managing-global-thresholds.html
related:
  - title: Managing Merchant Order Thresholds
    link: docs/scos/user/back-office-user-guides/page.version/administration/thresholds/managing-merchant-order-thresholds.html
  - title: Managing Threshold Settings
    link: docs/scos/user/back-office-user-guides/page.version/administration/thresholds/managing-threshold-settings.html
---

This topic describes how to manage global thresholds.

## Prerequisites
To start working with global thresholds, go to **Administration&nbsp;<span aria-label="and then">></span> Global Threshold**.

Review the reference information before you start, or look up the necessary information as you go through the process.

## Define a minimum hard threshold

1. On the **Edit Global threshold** page, select the **STORE AND CURRENCY** you want to define the threshold for.
2. In the **Minimum Hard Threshold** pane, for **ENTER THRESHOLD VALUE**, enter a price value.
3. Enter a **MESSAGE** for all the locales.
4. Scroll down the page and click **Save**.

The page refreshes with a success message displayed.

## Define a maximum hard threshold

1. On the **Edit Global threshold** page, select the **STORE AND CURRENCY** you want to define the threshold for.
2. In the **Maximum Hard Threshold** pane, for **ENTER THRESHOLD VALUE**, enter a price value.
3. Enter a **MESSAGE** for all the locales.
4. Scroll down the page and select **Save**.

The page refreshes with a success message displayed.

## Define a minimum soft threshold

1. On the **Edit Global threshold** page, select the **STORE AND CURRENCY** you want to define the threshold for.
2. In the **Soft Threshold** pane, select a soft threshold type.
3. For **ENTER THRESHOLD VALUE**, enter a price value.
4. If you selected a threshold with fee, do one of the following:
   * **SOFT THRESHOLD WITH FIXED FEE**: For **ENTER FIXED FEE**, enter a price value.
   * **SOFT THRESHOLD WITH FLEXIBLE FEE**: For **ENTER FLEXIBLE FEE**, enter a price value.
5. Enter a **MESSAGE** for all the locales.
6. Select **Save**.

The page refreshes with a success message displayed.

## Setting up several thresholds

To set up several threshold types:
1. Enter the fields in the sections of the thresholds you want to set up by following the respective instructions:
    * [Setting up a Hard Minimum Threshold](#setting-up-minimum-hard-threshold)
    * [Setting up a Hard Maximum Threshold](#setting-up-maximum-hard-threshold)
    * [Setting up a Soft Minimum Threshold](#setting-up-minimum-soft-threshold)
2. Select **Save**.

The page refreshes, and the message about successful threshold update is displayed.

**Tips and tricks**
<br>In the **Message** field, enter *{% raw %}{{{% endraw %}threshold{% raw %}}}{% endraw %}* or *{% raw %}{{{% endraw %}fee{% raw %}}}{% endraw %}* to reference the threshold name or the defined fee, respectively. When the message is rendered on the Storefront, the placeholders are replaced with the values from **Enter threshold value** and **Enter flexible fee** or **Enter fixed fee** fields.

See  [Reference information](#reference-information) to know more about attributes.

## Reference information

The following table describes the attributes you select and enter when managing global order thresholds or when [managing merchant order thresholds](/docs/scos/user/back-office-user-guides/{{page.version}}/administration/thresholds/managing-merchant-order-thresholds.html).

| ATTRIBUTE |DESCRIPTION|
| --- | --- |
| STORE AND CURRENCY | Defines the store to which the threshold is applied and the currency in which it is displayed. |
| ENTER THRESHOLD VALUE | Depending on the threshold type, defines the value that should be reached or not reached.|
|MESSAGE |Short message that informs the customer about the threshold conditions. For example, _You should add items for {% raw %}{{{% endraw %}threshold{% raw %}}}{% endraw %} to pass a recommended threshold. You can't proceed with checkout._ <br><br> Enter {% raw %}{{{% endraw %}threshold{% raw %}}}{% endraw %} or {% raw %}{{{% endraw %}fee{% raw %}}}{% endraw %} to reference the threshold name or the defined fee respectively. When the message is rendered on the Storefront, the placeholders are replaced with the values from **Enter threshold value** and **Enter flexible fee** or **Enter fixed fee** fields. |
| ENTER FIXED FEE | Adds this value to cart if the threshold is not reached. |
| ENTER FLEXIBLE FEE | Percentage of an order's sub-total that is added to cart if the threshold is not reached.|