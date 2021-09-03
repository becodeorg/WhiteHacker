# Monitoring and Logs analysis

Type of challenge : **Learning/Practice**

Duration : **8 hours**

Team Challenge : **solo**

## Learning objectives

At the end of this briefing you should be able to :
- log reporting to Azure log analytics
- run custom actions on event

## Your mission

Many accounts of Becloud have been hacked recently. Hackers from China and Russia are brute forcing passwords of your employees with success. Each time an employee is flagged as risky, you need to take many actions manually in order to guarantee that if the account is corrupted at some point, the hacker won't have access to too much data and we would know which one has been accessed.

This task is really time consuming and isn't done as soon as a user is flagged but rather when someone from the support team notice it. It represent a risk and a time consuming task for an already reduced team.

Your mission will be to automate the following actions on each risky sign-ins, or when a user is flagged as risky and to setup rules avoiding logins from China and Russia since none of our employees are working in these countries.

- Reset password to a secure one
- Kill all active sessions
- Enable MFA
- Produce an audit log of the actions that the user took

### Instructions

- Check the documentation about :
    - ["Log Analytics Workspace"](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace)
    - ["Risky Sign-ins"](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-sign-ins)
    - ["Automation"](https://docs.microsoft.com/en-us/azure/automation/)
- Check how you can import sign-ins and audit into azure analytics
- Check how you can link an alert with an automation runbook
- Write a script doing the asked tasks to mitigate risky sign-ins
- Link your automation workbook and the script
- Try it out (to simulate logins from China, you can use a vpn or just block connections from outside Belgium and use Tor to mask your ip)

## Trusty Resources
- ["Log Analytics Workspace"](https://docs.microsoft.com/en-us/azure/azure-monitor/logs/quick-create-workspace)
- ["Risky Sign-ins"](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-sign-ins)
- ["Automation"](https://docs.microsoft.com/en-us/azure/automation/)
