# Monitoring Metrics and Logs in Microsoft Azure

Type of challenge : **Learning/Practice**

Duration : **8 hours**

Team Challenge : **solo**

## Learning objectives

At the end of this briefing you should be able to :
- Enable diagnostic monitoring for azure resources
- View metrics across subscriptions
- Create alerts across subscriptions
- Analyse logs in Azure Monitor Log Analytics

## Preamble
In this briefing, you will learn how to enable diagnostic monitoring for various Azure resources, whether we're talking about storage accounts or virtual machines or databases or web apps. You need to know where to go to turn on those log and metric streams so that you can then take advantage of that feedback in making good decisions with those resources. By the end of this briefing, you should know how to view metrics across subscriptions.

You will also have to to create alerts, and then we'll even get into Azure Monitor Log Analytics, which is a really amazing platform that has its own unified query language.

The two main tool that you will have to focus on, will be :

- The Metrics Explorer in Azure Monitor
- Azure Monitor Log Analytics

## Your mission

Before doing anything you should first learn about :
- [Azure Monitor Metrics overview](https://docs.microsoft.com/en-us/azure/azure-monitor/essentials/data-platform-metrics)
- [Getting started with Azure Metrics Explorer](https://docs.microsoft.com/en-us/azure/azure-monitor/essentials/metrics-getting-started)
- [Log Analytics in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-overview)
- [Create a metrics chart in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/essentials/tutorial-metrics-explorer)

Then depending on the resources you have previously deployed on Azure, for each of these you will have to enable Diagnostics, collects relevant Metrics and/or Logs and send them to the Azure Log Analytics. Of course you should select which specific metric you want to collect. To finish, use Azure Monitor to create one or two simple charts to visualize the data metrics data you collected.

When you have setup all that, you will have to share with us (2min presentation) of which metric/log data are you collecting and explain why did you choose these metrics over some others. During the presentation, fell free to share your learning experience or any additional information that could be benificial to the others :)

## Trusty Resources
- [Azure Monitor Metrics Data Sources](https://docs.microsoft.com/en-us/azure/azure-monitor/agents/data-sources)
- [Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/)
