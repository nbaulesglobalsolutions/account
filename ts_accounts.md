---

copyright:

  years: 2015, 2018

lastupdated: "2018-07-16"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}


# Troubleshooting for managing accounts
{: #managingaccounts}

General problems with managing your account might include different apps share the same domain name, or administrators can't view all organizations. In many cases, you can recover from these problems by following a few easy steps.
{:shortdesc}

## Unable to access a different {{site.data.keyword.Bluemix_notm}} region
{: #nosecondreg}

You receive an error message when you try to create a new {{site.data.keyword.Bluemix_notm}} region.
{: tsSymptoms}

This is likely because you are using a Lite account, which supports development in one public region only. You select the {{site.data.keyword.Bluemix_notm}} public region in which you want to work when the account is first set up.
{: tsCauses}

If you have a Lite account, you can upgrade to a billable account to access additional regions. Go to the **Manage > Billing and Usage > Billing** page in the console, and click **Add Credit Card**. On the **Billing** page, you can also check if you have a Lite account.
{: tsResolve}

## Unable to create new organization
{: #nosecondorg}

You receive an error message when you try to create a new organization.
{: tsSymptoms}

This is likely because you are using a Lite account, which supports development in one organization only. You create the organization when your account is first set up.
{: tsCauses}

If you have a Lite account, you can upgrade to a billable account to access additional organizations. Go to the **Manage > Billing and Usage > Billing** page in the console, and click **Add Credit Card**. On the **Billing** page, you can also check if you have a Lite account.
{: tsResolve}

## Unable to create Lite plan instance
{: #nosecondlite}

You receive the following error message when you try to create a Lite plan instance:
{: tsSymptoms}

`Unable to provision new Lite instance`

There is a limit of one instance per Lite plan instance to allow us to keep these plans free.
{: tsCauses}

You can create additional instances of the service by selecting one of the billable service plans, which are available in the billable accounts. To upgrade to a billable account from the console, go to the **Manage > Billing and Usage > Billing** page, and click **Add Credit Card**.
{: tsResolve}

If you do not want to upgrade from a Lite account and are no longer using your existing Lite service instance, you can delete the existing Lite plan instance from the dashboard and then create a new instance.

## Exceeded the runtime memory allowance
{: #noruntimemem}

You are unable to deploy apps and get an error stating that you have exceeded your organization's memory limit.
{: tsSymptoms}

In a Lite account your Cloud Foundry apps can use up to 256 MB of instantaneous runtime memory. In billable accounts, there is a 2GB memory limit.
{: tsCauses}

If you are using a Lite account, you can get additional memory by upgrading to a billable account. Go to the **Manage > Billing and Usage > Billing** page in the console, and click **Add Credit Card**.
{: tsResolve}

If you do not want to upgrade from a Lite account but have some idle apps, you can delete the idle apps to free up some runtime memory.

## Account is inactive
{: #ts_accnt_inactive}

You can't create an app in {{site.data.keyword.Bluemix_notm}} if your account is inactive. You must contact the support team to fix this problem.

When you try to create an app in {{site.data.keyword.Bluemix_notm}}, you see the following error message:
{: tsSymptoms}

`BXNUI0096E: The app wasn't created. Your account is inactive because it was canceled or suspended.`

The status of your {{site.data.keyword.Bluemix_notm}} account becomes inactive when the account is cancelled or suspended.
{: tsCauses}

To reactivate your account, contact [{{site.data.keyword.Bluemix_notm}} Support ![External link icon](../icons/launch-glyph.svg "External link icon")](http://ibm.biz/bluemixsupport.com){: new_window}. Include the following information in the email:
{: tsResolve}

  * The IBMid that you use to log in to {{site.data.keyword.Bluemix_notm}}.
  * The name of the organization in which your app is being created. This information can help the support team determine whether you are assigned the correct roles or membership in your organization.

## Can't add users to an org
{: #ts_adduser}

You can invite more than one user to work under the same organization. You can invite users to your organization only if you are the account owner, or if you are a manager of the organization.

You can't see the **Invite a New User** link in your **Manage Organizations** section.
{: tsSymptoms}

Only the following {{site.data.keyword.Bluemix_notm}} users can invite users to an organization:
{: tsCauses}
  * The account owner of the organization
  * Managers of the organization

**Note:** All organization managers can add, modify, and remove users that are already in the organization.

If you can't invite users to your organization, contact your organization manager. To identify your organization manager, complete the following steps:
{: tsResolve}

  1. From the console menu bar, click **Manage > Account > Organizations**.
  2. Go to your organization, and view the information of organization manager on the **USERS** tab.  

## Batch registration of users isn't supported
{: #ts_batchregistration}

When you register users for {{site.data.keyword.Bluemix_notm}}, you must register each user individually.

{{site.data.keyword.Bluemix_notm}} doesn't provide the capability to register multiple users at the same time.
{: tsSymptoms}

{{site.data.keyword.Bluemix_notm}} doesn't support batch registration of users. To register users for {{site.data.keyword.Bluemix_notm}}, you must register each user individually.
{: tsCauses}

To register multiple users for {{site.data.keyword.Bluemix_notm}}, complete the following steps for each user:
{: tsResolve}

  1. Click **SIGN UP** in the {{site.data.keyword.Bluemix_notm}} console.
  2. Complete the steps by following the wizard.

## No space is associated with your current org
{: #ts_no_space}

You can't create an app if no space is associated with your current organization.

When you try to create an app in {{site.data.keyword.Bluemix_notm}}, you see the following error message:
{: tsSymptoms}

`BXNUI0097E: Before you can add an app, at least one space must be associated with your organization and region. On the Dashboard, click Create a Space. When the space is created, try again.`

Apps in {{site.data.keyword.Bluemix_notm}} must be created in a space under your organization.
{: tsCauses}

To create a space, use one of the following methods:
{: tsResolve}

  * From the console menu bar, click **Manage > Account > Organizations**. Then, select the organization in which you want to create the space, and click **Create a Space**.
  * In the Cloud Foundry command line interface, type `cf create-space <space_name> -o <organization_name>`.


## Apps share the same domain name
{: #ts_domain_diff}

You might notice that several apps share the same URL in {{site.data.keyword.Bluemix_notm}}.

This problem might happen when you assign the same URL route for different apps in a space.
{: tsCauses}

For example, you push the myApp1 app to {{site.data.keyword.Bluemix_notm}} and set the domain to "mynewapp.stage1.mybluemix.net". Then, you push another myApp2 app to the same space and set one of its URL routes to "mynewapp.stage1.mybluemix.net". The route is now mapped to both apps.

This is supported behavior of the {{site.data.keyword.Bluemix_notm}} and you can use this practice to achieve zero downtime for your app upgrade. For more information, see [Using Blue-Green Deployment to Reduce Downtime and Risk ![External link icon](../icons/launch-glyph.svg "External link icon")](https://docs.cloudfoundry.org/devguide/deploy-apps/blue-green.html){: new_window}.
{: tsResolve}


## Administrators can't view all orgs by using the {{site.data.keyword.Bluemix_notm}} user interface
{: #ts_ui_org}

As an administrator, when you use the {{site.data.keyword.Bluemix_notm}} user interface, you can't display every organization to administer them. You can display and administer only those organizations to which you belong.

As an administrator, you can't see all the organizations by using the {{site.data.keyword.Bluemix_notm}} user interface.
{: tsSymptoms}

This is a limitation of the {{site.data.keyword.Bluemix_notm}} user interface.
{: tsCauses}

You can use commands such as `cf orgs`, `cf create-org`, and `cf delete-org` from the Cloud Foundry command line interface to manage all the organizations. For a full list of cf commands, enter `cf help`.
{: tsResolve}

## Credit card can't be added
{: #ts_addcc}

You can't submit your credit card information to convert your Lite account to a billable account.

The **Submit** button on the Add credit card page is disabled.
{: tsSymptoms}

This problem happens when your information isn't filled in correctly in the Add credit card page.
{: tsCauses}


Complete the following steps:
{: tsResolve}

  1. On the Add credit card page, fill in all the required fields in the contact information, contact address, and billing address sections.
  2. Select **I have read and agree to IBM's Terms and Conditions**, then click **Submit**. The **Select a payment method** section is displayed.
  3. Enter your credit card number, the expiry date of your card, and the security code on your card. Then click **Submit**.
