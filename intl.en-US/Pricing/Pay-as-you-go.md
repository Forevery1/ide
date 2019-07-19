# Pay-as-you-go {#concept_264774 .concept}

After activating DataWorks in pay-as-you-go mode, you can develop nodes, run nodes on a scheduled basis, schedule data sync nodes, monitor a large number of workflows, monitor data quality, call APIs that are compiled in DataService Studio, debug code in the App Studio development environment, and perform other operations.

**Note:** When using DataWorks for the first time, you must activate DataWorks in pay-as-you-go mode. This gives you access to all the basic functions of DataWorks at the lowest cost, enabling you to experience the all-in-one data development process.

## Billing items {#section_1ww_j0o_r27 .section}

When DataWorks is activated in pay-as-you-go mode, the following billing items apply:

-   Shared resource groups for scheduling
-   Shared resource groups for Data Integration instances
-   Baseline instances generated by Intelligent Monitor
-   Data Quality checks
-   Calls and execution time of APIs compiled in DataService Studio
-   App Studio development environment

**Note:** 

-   You are billed only when you use these resources.
-   After you activate these billing items, the system automatically activates DataWorks Basic Edition for free.
-   If you perform a smoke test in the development environment, instances are generated and billed.

For more information, see [DataWorks Pay-As-You-Go mode details](intl.en-US/Pricing/Appendix/DataWorks Pay-As-You-Go mode details.md#).

## Shared resource groups for scheduling {#section_58d_999_h12 .section}

-   Billing range

    All instances generated by nodes \(except the instances generated by virtual nodes\) that are submitted to the scheduling system are included in the billing range. The instances include auto triggered instances, manually triggered instances, test instances, and retroactive instances.

-   Billing standard

    This billing item is billed daily based on a tiered pricing schedule according to the number of instances run per day. The billing standard is listed in the following table.

    |Region|Minimum number of instances|Maximum number of instances|Billing cycle|Fee \(USD/day\)|
    |------|---------------------------|---------------------------|-------------|---------------|
    |China \(Hangzhou\) China \(Shanghai\)

 China \(Beijing\)

 China \(Shenzhen\)

 Hong Kong

 |1|10|Daily|0.00|
    |11|500|Daily|0.15|
    |501|5,000|Daily|9.29|
    |5,001|20,000|Daily|23.22|
    |20,001|50,000|Daily|41.79|
    |50,001|120,000|Daily|92.87|
    |Singapore Australia \(Sydney\)

 Malaysia \(Kuala Lumpur\)

 Indonesia \(Jakarta\)

 Japan \(Tokyo\)

 US \(Silicon Valley\)

 US \(Virginia\)

 Germany \(Frankfurt\)

 UK \(London\)

 UAE \(Dubai\)

 |1|10|Daily|0.00|
    |11|500|Daily|0.23|
    |501|5,000|Daily|13.93|
    |5,001|20,000|Daily|34.82|
    |20,001|50,000|Daily|62.68|
    |50,001|120,000|Daily|139.30|

    **Note:** 

    -   Only instances that have been run in **O&M Center** \> **Task O&M** are billed. Instances that have been generated but not run, instances that are frozen, and dry-run instances are not billed.
    -   If the number of instances per day exceeds 120,000, the excess instances cannot be scheduled. If your actual business volume exceeds this threshold, open a ticket to seek help from Alibaba Cloud Customer Services.
-   Deduction method

    Starting at 00:00 every day, the billing system settles the number of instances that were run in the previous calendar day and deducts fees based on only one of the pricing tiers specified in the preceding billing standard. No additional fees are generated.

    Assume that you deploy a DataWorks workspace in China \(Shanghai\) and run 502 instances on April 30, 2019. The billing system deducts a fee of 9.26 USD from your account balance after 00:00 on May 1, 2019.

-   Overdue payments

    If payment for your account becomes overdue, you are given a 360-hour grace period. The billing system sends a notification at the 192nd, 288th, and 336th hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 360 hours, the service will be suspended. At this time, any instances that have not run cannot be started, but the running instances can be retained until they are finished.
    -   If you recharge your account within 360 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 360 hours after it enters into arrears.

## Shared resource groups for Data Integration instances {#section_6c6_037_383 .section}

-   Billing range

    The billing system bills the concurrent instances that are generated and run successfully when Data Integration nodes run in auto-triggered instances, retroactive instances, manually triggered instances, DataStudio workflow, or smoke testing mode.

    **Note:** Data Integration instances consume both shared resource groups for Data Integration instances \(pay-as-you-go\) and shared resource groups for scheduling \(pay-as-you-go\).

-   Billing standard

    This billing item is billed daily based on a tiered pricing schedule according to the number of concurrent instances generated when Data Integration nodes are scheduled per day. The billing standard is listed in the following table.

    |Region|Minimum number of instances|Maximum number of instances|Billing cycle|Fee \(USD/day\)|
    |------|---------------------------|---------------------------|-------------|---------------|
    |China \(Hangzhou\)|1|10|Daily|0.00|
    |China \(Shanghai\)|11|500|Daily|0.15|
    |China \(Beijing\)|501|5,000|Daily|0.93|
    |China \(Shenzhen\)|5,001|20,000|Daily|3.10|
    |Hong Kong|20,001|50,000|Daily|7.74|
    | |50,001|120,000|Daily|15.48|
    |Singapore Australia \(Sydney\)

 Malaysia \(Kuala Lumpur\)

 Indonesia \(Jakarta\)

 Japan \(Tokyo\)

 US \(Silicon Valley\)

 US \(Virginia\)

 Germany \(Frankfurt\)

 UK \(London\)

 UAE \(Dubai\)

 |1|10|Daily|0.00|
    |11|500|Daily|0.23|
    |501|5,000|Daily|1.39|
    |5,001|20,000|Daily|4.64|
    |20,001|50,000|Daily|11.61|
    |50,001|120,000|Daily|23.22|

    **Note:** If the number of instances per day exceeds 120,000, the excess instances cannot be scheduled. If your actual business volume exceeds this threshold, open a ticket to seek help from Alibaba Cloud Customer Services.

-   Deduction method

    Starting at 00:00 every day, the billing system settles the number of instances that were run in the previous calendar day and deducts fees based on only one of the pricing tiers specified in the preceding billing standard. No additional fees are generated.

    Assume that you configure two sync nodes \(nodes A and B\) in your DataWorks workspace in China \(Shanghai\) and use shared resources to run these nodes. If you set the concurrency of node A to 2 and schedule it on a daily basis, the system generates one instance every day. If you set the concurrency of node B to 5 and schedule it on an hourly basis, the system generates 24 instances every day.

    If all node instances run, you are billed as follows:

    1.  Total concurrent instances settled each day: `2 x 1 + 5 x 24 = 122`.
    2.  The number of daily concurrent instances is 122, which is in the 11 to 500 tier. According the price for this tier, you are charged a daily fee of 0.15 USD.
-   Overdue payments

    If payment for your account becomes overdue, you are given a 360-hour grace period. The billing system sends a notification at the 192nd, 288th, and 336th hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 360 hours, the service will be suspended. At this time, any instances that have not run cannot be started, but the running instances can be retained until they are finished.
    -   If you recharge your account within 360 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 360 hours after it enters into arrears.

## Public network traffic of Data Integration instances {#section_qvr_1d5_hpo .section}

-   Billing range

    When Data Integration nodes are run in shared resource groups or on exclusive resources, the public network traffic they generate is billed on a pay-as-you-go basis. The unit price is 0.12 USD/GB.

    **Note:** When public network traffic is generated, DataWorks does not charge for the public network traffic generated by nodes running in custom resource groups. You may be billed for the public network traffic generated by other cloud products during data transmission, depending on the pricing policies of the corresponding products.

-   Deduction method

    The billing system calculates your fee for the previous hour and generates a bill at the start of each hour. Then, the actual fee is deducted from the balance of your Alibaba Cloud primary account.

    For example, the billing system bills you at 9:30 for the charges incurred from 08:00 to 09:00.

-   Overdue payments

    If payment for your account becomes overdue, you are given a 360-hour grace period. The billing system sends a notification at the 192nd, 288th, and 336th hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 360 hours, the service will be suspended. At this time, any instances that have not run cannot be started, but the running instances can be retained until they are finished.
    -   If you recharge your account within 360 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 360 hours after it enters into arrears.

## Calls and execution time of APIs compiled in DataService Studio {#section_754_42t_n0g .section}

-   Billing range

    The billing system bills the calls and execution time of APIs that are complied in DataService Studio. All users receive a free quota each month. The billing system bills for only valid calls to APIs compiled in DataService Studio, including online test calls.

    -   Valid calls are API requests that receive a response with an error code of 0.
    -   Invalid calls are API requests that receive a response with an error code other than 0.
-   Billing standard

    |Billing item|Unit|Unit price|Remarks|
    |------------|----|----------|-------|
    |Number of API calls|Million calls|0.21 USD/million requests|None|
    |Execution time|Memory × seconds \(GB×s\)|0.000017193 USD/GB\*s|The minimum unit of time that the billing system bills is 100 ms. A time shorter than 100 ms is calculated as 100 ms.|

    DataService Studio provides a free quota for each user every month. The RAM users share the monthly free quota with the primary account.

    -   Number of API calls: The first 1 million calls that a user makes per month are free.
    -   Execution time: The first 400,000 GB\*s of API call execution time for each user is free each month.
    **Note:** The free quota is recalculated at the start of each new month. Any remaining quota from the previous month does not roll over.

    For example, if you make 10 million API calls this month, and each call occupies 2 GB and takes 1,060 ms, you will be charged as follows:

    -   Monthly API calls and fees

        You receive a free quota of 1 million calls per month, so the number of API calls to be billed this month is 10 million - 1 million = 9 million. The price for every 1 million calls is 0.21 USD, so the total API call fee for this month is `900/100 x 0.21 = 1.89` USD.

    -   Monthly execution time and fee

        The API call execution time is measured in memory \(GB\) × seconds, that is, GB×s. The minimum unit of time that the billing system bills is 100 ms. A time shorter than 100 ms is calculated as 100 ms.

        Your total API call execution time = Number of calls × Memory consumed per call \(GB\) × Running time per call \(seconds\) = `10,000,000 × 2 × 1.1 = 22,000,000`GB×s. You receive a free API call execution time quota of 400,000 GB×s each month, so the actual API call execution time to be billed is `22,000,000 - 400,000 = 21,600,000`GB×s. If the price per GB×s of API call execution time is 0.000017193 USD, the fee for the total API call execution time for this month is `21,600,000 × 0.000017193 = 371.37` USD.

    -   Total monthly fee

        Total monthly fee =Monthly API call fee + Monthly execution time fee, that is `1.89 + 371.37 = 373.26` USD.

-   Deduction method

    DataService Studio has an hourly billing cycle. The billing system calculates your fee for the previous hour and generates a bill at the start of each hour. Then, the actual fee is deducted from the balance of your Alibaba Cloud primary account.

-   Overdue payments

    If payment for your account becomes overdue, you are given a 360-hour grace period. The billing system sends a notification at the 192nd, 288th, and 336th hours, reminding you to renew your account as soon as possible.

    -   If the payment is overdue for more than 360 hours, the service will be suspended and you will be unable to call the released APIs normally.
    -   If you recharge your account within 360 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 360 hours after it enters into arrears.

## Data Quality checks {#section_a0u_dk2_u5c .section}

-   Billing range

    The billing system bills the Data Quality checks that are successfully generated by Data Quality within each calendar day. Such Data Quality checks are generated when related Data Quality rules run in auto-triggered instances, retroactive instances, or trial run mode.

-   Billing standard \(currently free of charge\)

    |Data Quality checks per day|Price \(USD/day\)|
    |---------------------------|-----------------|
    |1 to 10|0.00|
    |11 to 200|3.10|
    |201 to 1,000|7.74|
    |1,001 to 5,000|30.96|
    |5,000 to 10,000|46.43|

-   Deduction method

    Starting at 00:00 every day, the billing system settles the number of instances that were run in the previous calendar day and deducts fees based on only one of the pricing tiers specified in the preceding billing standard. No additional fees are generated.

    -   Successful running refers to the successful implementation of the rule itself. A rule is considered successfully implemented if alerts are reported or workflows are blocked due to data quality problems.
    -   The pay-as-you-go limit for Data Quality checks is 5,000. After this threshold is reached, Data Quality checks stop running. If you need more Data Quality checks per day, open a ticket to seek help from Alibaba Cloud Customer Services.
-   Overdue payments

    If payment for your account becomes overdue, you are given a 24-hour grace period. The billing system sends a notification at the 12th and 23rd hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 24 hours, the service will be suspended. In this case, you cannot start new Data Quality checks, but any Data Quality checks that are already started are not affected.
    -   If you recharge your account within 24 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 24 hours after it enters into arrears.

## Baseline instances generated by Intelligent Monitor {#section_2pl_gyi_qo1 .section}

-   Billing range

    All enabled baselines generate baseline instances and you are billed based on the number of baseline instances generated before 23:59 each day.

-   Billing standard \(currently free of charge\)

    |Baseline instances per day|Price \(USD/day\)|
    |--------------------------|-----------------|
    |1 to 2|0.00|
    |3 to 10|0.77|
    |11 to 100|3.10|

-   Deduction method

    Starting at 00:00 every day, the billing system settles the number of baseline instances that were run in the previous business day and deducts fees based on only one of the pricing tiers specified in the preceding billing standard. No additional fees are generated.

    -   The billing system calculates one baseline instance for an hourly baseline of an hourly task.
    -   The pay-as-you-go limit for enabled baselines is 100. After this threshold is reached, no more baseline instances can be generated. If you need more baseline instances, open a ticket to seek help from Alibaba Cloud Customer Services.
-   Overdue payments

    If payment for your account becomes overdue, you are given a 24-hour grace period. The billing system sends a notification at the 12th and 23rd hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 24 hours, the service will be suspended. In this case, no more baseline instances can be generated, but baseline instances that are already started are not affected.
    -   If you recharge your account within 24 hours after your bill becomes overdue, the service will not be suspended. If the service payment becomes overdue again after settlement, the service will be suspended 24 hours after it enters into arrears.

## App Studio development environment {#section_axb_3wg_i0s .section}

-   Billing standard

    This billing item charges code debugging time in the App Studio development environment on an hourly basis. This billing standards are listed in the following table.

    |App Studio development environment|Code debugging fee \(USD/hour\)|Region|
    |----------------------------------|-------------------------------|------|
    |1c2g|0.12|China \(Shanghai\) China \(Hangzhou\)

 China \(Shenzhen\)

 China \(Beijing\)

 |
    |2c4g|0.25|
    |4c8g|0.50|
    |8c16g|0.99|

    **Note:** The first 2 billable hours of each month are free of charge. The conversion between billable hours and hours is listed in the following table.

    |App Studio development environment|Actual debugging time \(hours\)|Consumed billable hours|
    |----------------------------------|-------------------------------|-----------------------|
    |1c2g|1|1|
    |2c4g|1|2|
    |4c8g|1|4|
    |8c16g|1|8|

-   Deduction method

    Billing starts when you start code debugging and ends when the code debugging ends.

    If you modify the instance specifications in the debugging configuration, the debugging fee is billed according to the corresponding configuration.

-   Overdue payments

    If payment for your account becomes overdue, you are given a 24-hour grace period. The billing system sends a notification at the 12th and 23rd hours, reminding you to renew your account as soon as possible.

    -   If your bill is overdue for more than 24 hours, the service will be suspended. If you are currently debugging at this time, the current process will not be interrupted. However, once you stop, the debugging cannot be restored.
    -   If you recharge your account within 24 hours after your bill becomes overdue, the service will not be suspended.
    -   If the service payment becomes overdue again after settlement, the service will be suspended 24 hours after it enters into arrears.
