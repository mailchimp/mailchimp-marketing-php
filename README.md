# Mailchimp Marketing — PHP

The official PHP client library for the Mailchimp Marketing API

## Installation

**Option 1:** Install via Packagist
```
composer require mailchimp/marketing
```

Or add the following to `composer.json`
```
{
  "require": {
    "mailchimp/marketing": "*"
  }
}
```

Install all composer dependencies using:
```
composer install
```

**Option 2:** Install Manually

Clone the repo
```
git clone git@github.com:mailchimp/mailchimp-marketing-php.git
```

In the client library project root, install all dependencies
```
composer install
```

Manually include `vendor/autoload.php` in your implementation
```php
require_once('/path/to/MailchimpMarketing/vendor/autoload.php');
```

## Quick Start

```php
require_once('/path/to/MailchimpMarketing/vendor/autoload.php');

$mailchimp = new MailchimpMarketing\ApiClient();

$mailchimp->setConfig([
  'apiKey' => 'YOUR_API_KEY',
  'server' => 'YOUR_SERVER_PREFIX'
]);

$response = $mailchimp->ping->get();
print_r($response);
```

## Authentication Methods

The client library can be configured to use either **Basic Auth** or **OAuth2**.

For either method, a server prefix should be passed in i.e. `us19`, in order for the client to determine to appropriate host url.

### Basic Auth
```php
$mailchimp->setConfig([
  'apiKey' => 'YOUR_API_KEY',
  'server' => 'YOUR_SERVER_PREFIX'
]);
```

### OAuth2
```php
$mailchimp->setConfig([
  'accessToken' => 'YOUR_ACCESS_TOKEN',
  'server' => 'YOUR_SERVER_PREFIX'
]);
```

## API Endpoints

All URIs are relative to *https://server.api.mailchimp.com/3.0*

| Method | Endpoint |
| ---------- | -------- |
| **activityFeed.get** | /activity-feed |
| **activityFeed.getChimpChatter** | /activity-feed/chimp-chatter |
| **authorizedApps.list** | /authorized-apps |
| **authorizedApps.get** | /authorized-apps/{app_id} |
| **authorizedApps.link** | /authorized-apps |
| **automations.archive** | /automations/{workflow_id}/actions/archive |
| **automations.deleteWorkflowEmail** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.list** | /automations |
| **automations.get** | /automations/{workflow_id} |
| **automations.listAllWorkflowEmails** | /automations/{workflow_id}/emails |
| **automations.getWorkflowEmail** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.getWorkflowEmailSubscriberQueue** | /automations/{workflow_id}/emails/{workflow_email_id}/queue |
| **automations.getWorkflowEmailSubscriber** | /automations/{workflow_id}/emails/{workflow_email_id}/queue/{subscriber_hash} |
| **automations.listWorkflowEmailSubscribersRemoved** | /automations/{workflow_id}/removed-subscribers |
| **automations.getRemovedWorkflowEmailSubscriber** | /automations/{workflow_id}/removed-subscribers/{subscriber_hash} |
| **automations.updateWorkflowEmail** | /automations/{workflow_id}/emails/{workflow_email_id} |
| **automations.update** | /automations/{workflow_id} |
| **automations.create** | /automations |
| **automations.pauseAllEmails** | /automations/{workflow_id}/actions/pause-all-emails |
| **automations.startAllEmails** | /automations/{workflow_id}/actions/start-all-emails |
| **automations.pauseWorkflowEmail** | /automations/{workflow_id}/emails/{workflow_email_id}/actions/pause |
| **automations.startWorkflowEmail** | /automations/{workflow_id}/emails/{workflow_email_id}/actions/start |
| **automations.addWorkflowEmailSubscriber** | /automations/{workflow_id}/emails/{workflow_email_id}/queue |
| **automations.removeWorkflowEmailSubscriber** | /automations/{workflow_id}/removed-subscribers |
| **batchWebhooks.remove** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.get** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.list** | /batch-webhooks |
| **batchWebhooks.update** | /batch-webhooks/{batch_webhook_id} |
| **batchWebhooks.create** | /batch-webhooks |
| **batches.deleteRequest** | /batches/{batch_id} |
| **batches.list** | /batches |
| **batches.status** | /batches/{batch_id} |
| **batches.start** | /batches |
| **campaignFolders.remove** | /campaign-folders/{folder_id} |
| **campaignFolders.list** | /campaign-folders |
| **campaignFolders.get** | /campaign-folders/{folder_id} |
| **campaignFolders.update** | /campaign-folders/{folder_id} |
| **campaignFolders.create** | /campaign-folders |
| **campaigns.remove** | /campaigns/{campaign_id} |
| **campaigns.deleteFeedbackMessage** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.list** | /campaigns |
| **campaigns.get** | /campaigns/{campaign_id} |
| **campaigns.getContent** | /campaigns/{campaign_id}/content |
| **campaigns.getFeedback** | /campaigns/{campaign_id}/feedback |
| **campaigns.getFeedbackMessage** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.getSendChecklist** | /campaigns/{campaign_id}/send-checklist |
| **campaigns.update** | /campaigns/{campaign_id} |
| **campaigns.updateFeedbackMessage** | /campaigns/{campaign_id}/feedback/{feedback_id} |
| **campaigns.create** | /campaigns |
| **campaigns.cancelSend** | /campaigns/{campaign_id}/actions/cancel-send |
| **campaigns.createResend** | /campaigns/{campaign_id}/actions/create-resend |
| **campaigns.pause** | /campaigns/{campaign_id}/actions/pause |
| **campaigns.replicate** | /campaigns/{campaign_id}/actions/replicate |
| **campaigns.resume** | /campaigns/{campaign_id}/actions/resume |
| **campaigns.schedule** | /campaigns/{campaign_id}/actions/schedule |
| **campaigns.send** | /campaigns/{campaign_id}/actions/send |
| **campaigns.sendTestEmail** | /campaigns/{campaign_id}/actions/test |
| **campaigns.unschedule** | /campaigns/{campaign_id}/actions/unschedule |
| **campaigns.addFeedback** | /campaigns/{campaign_id}/feedback |
| **campaigns.setContent** | /campaigns/{campaign_id}/content |
| **connectedSites.remove** | /connected-sites/{connected_site_id} |
| **connectedSites.list** | /connected-sites |
| **connectedSites.get** | /connected-sites/{connected_site_id} |
| **connectedSites.create** | /connected-sites |
| **connectedSites.verifyScriptInstallation** | /connected-sites/{connected_site_id}/actions/verify-script-installation |
| **conversations.list** | /conversations |
| **conversations.get** | /conversations/{conversation_id} |
| **conversations.getConversationMessages** | /conversations/{conversation_id}/messages |
| **conversations.getConversationMessage** | /conversations/{conversation_id}/messages/{message_id} |
| **conversations.createConversationMessage** | /conversations/{conversation_id}/messages |
| **ecommerce.deleteStore** | /ecommerce/stores/{store_id} |
| **ecommerce.deleteStoreCart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.deleteCartLineItem** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.deleteStoreCustomer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.deleteOrder** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.deleteOrderLineItem** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.deleteStoreProduct** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.deleteProductImage** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.deleteProductVariant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.deletePromoCode** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.deletePromoRule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.info** | /ecommerce |
| **ecommerce.orders** | /ecommerce/orders |
| **ecommerce.stores** | /ecommerce/stores |
| **ecommerce.getStore** | /ecommerce/stores/{store_id} |
| **ecommerce.getStoreCarts** | /ecommerce/stores/{store_id}/carts |
| **ecommerce.getStoreCart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.getAllCartLineItems** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines |
| **ecommerce.getCartLineItem** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.getAllStoreCustomers** | /ecommerce/stores/{store_id}/customers |
| **ecommerce.getStoreCustomer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.getStoreOrders** | /ecommerce/stores/{store_id}/orders |
| **ecommerce.getOrder** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.getAllOrderLineItems** | /ecommerce/stores/{store_id}/orders/{order_id}/lines |
| **ecommerce.getOrderLineItem** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.getAllStoreProducts** | /ecommerce/stores/{store_id}/products |
| **ecommerce.getStoreProduct** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.getProductImages** | /ecommerce/stores/{store_id}/products/{product_id}/images |
| **ecommerce.getProductImage** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.getProductVariants** | /ecommerce/stores/{store_id}/products/{product_id}/variants |
| **ecommerce.getProductVariant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.getPromoCodes** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes |
| **ecommerce.getPromoCode** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.listPromoRules** | /ecommerce/stores/{store_id}/promo-rules |
| **ecommerce.getPromoRule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.updateStore** | /ecommerce/stores/{store_id} |
| **ecommerce.updateStoreCart** | /ecommerce/stores/{store_id}/carts/{cart_id} |
| **ecommerce.updateCartLineItem** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines/{line_id} |
| **ecommerce.updateStoreCustomer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.updateOrder** | /ecommerce/stores/{store_id}/orders/{order_id} |
| **ecommerce.updateOrderLineItem** | /ecommerce/stores/{store_id}/orders/{order_id}/lines/{line_id} |
| **ecommerce.updateStoreProduct** | /ecommerce/stores/{store_id}/products/{product_id} |
| **ecommerce.updateProductImage** | /ecommerce/stores/{store_id}/products/{product_id}/images/{image_id} |
| **ecommerce.updateProductVariant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **ecommerce.updatePromoCode** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes/{promo_code_id} |
| **ecommerce.updatePromoRule** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id} |
| **ecommerce.addStore** | /ecommerce/stores |
| **ecommerce.addStoreCart** | /ecommerce/stores/{store_id}/carts |
| **ecommerce.addCartLineItem** | /ecommerce/stores/{store_id}/carts/{cart_id}/lines |
| **ecommerce.addStoreCustomer** | /ecommerce/stores/{store_id}/customers |
| **ecommerce.addStoreOrder** | /ecommerce/stores/{store_id}/orders |
| **ecommerce.addOrderLineItem** | /ecommerce/stores/{store_id}/orders/{order_id}/lines |
| **ecommerce.addStoreProduct** | /ecommerce/stores/{store_id}/products |
| **ecommerce.addProductImage** | /ecommerce/stores/{store_id}/products/{product_id}/images |
| **ecommerce.addProductVariants** | /ecommerce/stores/{store_id}/products/{product_id}/variants |
| **ecommerce.addPromoCode** | /ecommerce/stores/{store_id}/promo-rules/{promo_rule_id}/promo-codes |
| **ecommerce.addPromoRules** | /ecommerce/stores/{store_id}/promo-rules |
| **ecommerce.setStoreCustomer** | /ecommerce/stores/{store_id}/customers/{customer_id} |
| **ecommerce.addProductVariant** | /ecommerce/stores/{store_id}/products/{product_id}/variants/{variant_id} |
| **facebookAds.list** | /facebook-ads |
| **facebookAds.getAd** | /facebook-ads/{outreach_id} |
| **fileManager.deleteFile** | /file-manager/files/{file_id} |
| **fileManager.deleteFolder** | /file-manager/folders/{folder_id} |
| **fileManager.get** | /file-manager |
| **fileManager.files** | /file-manager/files |
| **fileManager.getFile** | /file-manager/files/{file_id} |
| **fileManager.listFolders** | /file-manager/folders |
| **fileManager.getFolder** | /file-manager/folders/{folder_id} |
| **fileManager.updateFile** | /file-manager/files/{file_id} |
| **fileManager.updateFolder** | /file-manager/folders/{folder_id} |
| **fileManager.upload** | /file-manager/files |
| **fileManager.createFolder** | /file-manager/folders |
| **landingPages.deletePage** | /landing-pages/{page_id} |
| **landingPages.getAll** | /landing-pages |
| **landingPages.getPage** | /landing-pages/{page_id} |
| **landingPages.getPageContent** | /landing-pages/{page_id}/content |
| **landingPages.updatePage** | /landing-pages/{page_id} |
| **landingPages.create** | /landing-pages |
| **landingPages.publishPage** | /landing-pages/{page_id}/actions/publish |
| **landingPages.unpublishPage** | /landing-pages/{page_id}/actions/unpublish |
| **lists.deleteList** | /lists/{list_id} |
| **lists.deleteInterestCategory** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.deleteInterestCategoryInterest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.deleteListMember** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.deleteListMemberNote** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.deleteListMergeField** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.deleteSegment** | /lists/{list_id}/segments/{segment_id} |
| **lists.removeSegmentMember** | /lists/{list_id}/segments/{segment_id}/members/{subscriber_hash} |
| **lists.deleteListWebhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.getListMemberTags** | /lists/{list_id}/members/{subscriber_hash}/tags |
| **lists.getAllLists** | /lists |
| **lists.getList** | /lists/{list_id} |
| **lists.getListAbuseReports** | /lists/{list_id}/abuse-reports |
| **lists.getListAbuseReportDetails** | /lists/{list_id}/abuse-reports/{report_id} |
| **lists.getListRecentActivity** | /lists/{list_id}/activity |
| **lists.getListClients** | /lists/{list_id}/clients |
| **lists.getListGrowthHistory** | /lists/{list_id}/growth-history |
| **lists.getListGrowthHistoryByMonth** | /lists/{list_id}/growth-history/{month} |
| **lists.getListInterestCategories** | /lists/{list_id}/interest-categories |
| **lists.getInterestCategory** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.listInterestCategoryInterests** | /lists/{list_id}/interest-categories/{interest_category_id}/interests |
| **lists.getInterestCategoryInterest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.getListLocations** | /lists/{list_id}/locations |
| **lists.getListMembersInfo** | /lists/{list_id}/members |
| **lists.getListMember** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.getListMemberActivity** | /lists/{list_id}/members/{subscriber_hash}/activity |
| **lists.getListMemberActivityFeed** | /lists/{list_id}/members/{subscriber_hash}/activity-feed |
| **lists.getListMemberEvents** | /lists/{list_id}/members/{subscriber_hash}/events |
| **lists.getListMemberGoals** | /lists/{list_id}/members/{subscriber_hash}/goals |
| **lists.getListMemberNotes** | /lists/{list_id}/members/{subscriber_hash}/notes |
| **lists.getListMemberNote** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.getListMergeFields** | /lists/{list_id}/merge-fields |
| **lists.getListMergeField** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.getSegment** | /lists/{list_id}/segments/{segment_id} |
| **lists.getSegmentMembersList** | /lists/{list_id}/segments/{segment_id}/members |
| **lists.getListSignupForms** | /lists/{list_id}/signup-forms |
| **lists.getListWebhooks** | /lists/{list_id}/webhooks |
| **lists.getListWebhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.updateList** | /lists/{list_id} |
| **lists.updateInterestCategory** | /lists/{list_id}/interest-categories/{interest_category_id} |
| **lists.updateInterestCategoryInterest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests/{interest_id} |
| **lists.updateListMember** | /lists/{list_id}/members/{subscriber_hash} |
| **lists.updateListMemberNote** | /lists/{list_id}/members/{subscriber_hash}/notes/{note_id} |
| **lists.updateListMergeField** | /lists/{list_id}/merge-fields/{merge_id} |
| **lists.updateSegment** | /lists/{list_id}/segments/{segment_id} |
| **lists.updateListWebhook** | /lists/{list_id}/webhooks/{webhook_id} |
| **lists.createListMemberEvent** | /lists/{list_id}/members/{subscriber_hash}/events |
| **lists.updateListMemberTags** | /lists/{list_id}/members/{subscriber_hash}/tags |
| **lists.createList** | /lists |
| **lists.batchListMembers** | /lists/{list_id} |
| **lists.createListInterestCategory** | /lists/{list_id}/interest-categories |
| **lists.createInterestCategoryInterest** | /lists/{list_id}/interest-categories/{interest_category_id}/interests |
| **lists.addListMember** | /lists/{list_id}/members |
| **lists.deleteListMemberPermanent** | /lists/{list_id}/members/{subscriber_hash}/actions/delete-permanent |
| **lists.createListMemberNote** | /lists/{list_id}/members/{subscriber_hash}/notes |
| **lists.addListMergeField** | /lists/{list_id}/merge-fields |
| **lists.createSegment** | /lists/{list_id}/segments |
| **lists.batchSegmentMembers** | /lists/{list_id}/segments/{segment_id} |
| **lists.createSegmentMember** | /lists/{list_id}/segments/{segment_id}/members |
| **lists.updateListSignupForm** | /lists/{list_id}/signup-forms |
| **lists.createListWebhook** | /lists/{list_id}/webhooks |
| **lists.listSegments** | /lists/{list_id}/segments |
| **lists.previewSegment** | /lists/{list_id}/preview-segment |
| **lists.setListMember** | /lists/{list_id}/members/{subscriber_hash} |
| **ping.get** | /ping |
| **reporting.info** | /reporting |
| **reporting.getFacebookAdsReportAll** | /reporting/facebook-ads |
| **reporting.getFacebookAdReport** | /reporting/facebook-ads/{outreach_id} |
| **reporting.getFacebookAdProductActivityReport** | /reporting/facebook-ads/{outreach_id}/ecommerce-product-activity |
| **reporting.getLandingPageReportsAll** | /reporting/landing-pages |
| **reporting.getLandingPageReport** | /reporting/landing-pages/{outreach_id} |
| **reports.getAllCampaignReports** | /reports |
| **reports.getCampaignReport** | /reports/{campaign_id} |
| **reports.getCampaignAbuseReports** | /reports/{campaign_id}/abuse-reports |
| **reports.getCampaignAbuseReport** | /reports/{campaign_id}/abuse-reports/{report_id} |
| **reports.getCampaignAdvice** | /reports/{campaign_id}/advice |
| **reports.getCampaignClickDetails** | /reports/{campaign_id}/click-details |
| **reports.getCampaignClickDetailsForLink** | /reports/{campaign_id}/click-details/{link_id} |
| **reports.getSubscribersInfo** | /reports/{campaign_id}/click-details/{link_id}/members |
| **reports.getSubscriberInfo** | /reports/{campaign_id}/click-details/{link_id}/members/{subscriber_hash} |
| **reports.getDomainPerformanceForCampaign** | /reports/{campaign_id}/domain-performance |
| **reports.getEcommerceProductActivityForCampaign** | /reports/{campaign_id}/ecommerce-product-activity |
| **reports.getEepurlActivityForCampaign** | /reports/{campaign_id}/eepurl |
| **reports.getEmailActivityForCampaign** | /reports/{campaign_id}/email-activity |
| **reports.getEmailActivityForSubscriber** | /reports/{campaign_id}/email-activity/{subscriber_hash} |
| **reports.getLocationsForCampaign** | /reports/{campaign_id}/locations |
| **reports.getCampaignOpenDetails** | /reports/{campaign_id}/open-details |
| **reports.getSubscriberInfoForOpenedCampaign** | /reports/{campaign_id}/open-details/{subscriber_hash} |
| **reports.getCampaignRecipients** | /reports/{campaign_id}/sent-to |
| **reports.getCampaignRecipient** | /reports/{campaign_id}/sent-to/{subscriber_hash} |
| **reports.getSubReportsForCampaign** | /reports/{campaign_id}/sub-reports |
| **reports.getUnsubscribedListForCampaign** | /reports/{campaign_id}/unsubscribed |
| **reports.getUnsubscribedListMember** | /reports/{campaign_id}/unsubscribed/{subscriber_hash} |
| **root.getRoot** | / |
| **searchCampaigns.search** | /search-campaigns |
| **searchMembers.search** | /search-members |
| **templateFolders.remove** | /template-folders/{folder_id} |
| **templateFolders.list** | /template-folders |
| **templateFolders.get** | /template-folders/{folder_id} |
| **templateFolders.update** | /template-folders/{folder_id} |
| **templateFolders.create** | /template-folders |
| **templates.deleteTemplate** | /templates/{template_id} |
| **templates.list** | /templates |
| **templates.getTemplate** | /templates/{template_id} |
| **templates.getDefaultContentForTemplate** | /templates/{template_id}/default-content |
| **templates.updateTemplate** | /templates/{template_id} |
| **templates.create** | /templates |
| **verifiedDomains.createVerifiedDomain** | /verified-domains |
| **verifiedDomains.deleteDomain** | /verified-domains/{domain_name} |
| **verifiedDomains.getDomain** | /verified-domains/{domain_name} |
| **verifiedDomains.getVerifiedDomainsAll** | /verified-domains |
| **verifiedDomains.submitDomainVerification** | /verified-domains/{domain_name}/actions/verify |


## Additional Client Libraries

Mailchimp Marketing libraries are available in the following languages:

<div>
  <a href="https://github.com/mailchimp/mailchimp-marketing-node">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_node.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-php">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_php.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-ruby">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_ruby.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-marketing-python">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_python.png?raw=true" width="44" height="44">
  </a>
</div>
