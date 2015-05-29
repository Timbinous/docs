---
layout: page
weight: 0
title: FAQ
seo:
  title: Whitelabel FAQ
  description: Frequently asked questions about SendGrid Whitelabel
  keywords: whitelabel faq, domain whitelabel faq, email link faq
navigation:
  show: true
---

{% anchor h2 %}
Why whitelabel?
{% endanchor %}

Have you ever noticed that email you send through your SendGrid account displays “sent on behalf of” or “via sendgrid.me” and wondered how to get rid of it? Have you noticed that click-tracking links point to a SendGrid domain rather than your domain? Whitelabeling effectively masks SendGrid's delivery and click/open tracking to your domain, giving your emails a consistent and professional appearance where all links and sources point back to your domain.

{% anchor h2 %}
What is whitelabeling?
{% endanchor %}

The whitelabeling process involves the creation of several new DNS records including establishing a new subdomain (like em.example.com) in your domain registrar pointing to SendGrid. These DNS records ensure compliance with popular email standards, as well as give SendGrid express permission to deliver your mail by authenticating your outbound mail with your domain.

{% anchor h2 %}
Does whitelabeling require a certain type of account?
{% endanchor %}

[Domain]({{root_url}}/User_Guide/Settings/Whitelabel/domains.html) and [email link]({{root_url}}/User_Guide/Settings/Whitelabel/links.html) whitelabeling are available for all SendGrid users, no matter the account type. However, the IP whitelabeling process revolves around one central element: the dedicated IP address. Customers at SendGrid with a Pro account or higher are automatically assigned one dedicated IP address, which they whitelabel for their outbound mail. During this process, one of the DNS records that must be hosted is an A record, which specifies that all mail going out along this dedicated IP address is authorized to send mail on behalf of your domain.

{% anchor h2 %}
What is domain whitelabeling?
{% endanchor %}

[Domain whitelabeling]({{root_url}}/User_Guide/Settings/Whitelabel/domains.html) adds an SPF (Sender Policy Framework) record to your domain and DKIM (DomainKeys Identified Mail) entries, which effectively authorizes and authenticates SendGrid sending on behalf of your domain. Choosing SendGrid's new automated domain whitelabeling feature allows SendGrid the ability to securely manage your account’s DKIM and SPF records. Domain whitelabeling is the best way to get rid of the "sent on behalf of" or "via" message that some email providers display.

{% anchor h2 %}
What is email link whitelabeling?
{% endanchor %}

[Email Link whitelabeling]({{root_url}}/User_Guide/Settings/Whitelabel/links.html) adds a CNAME record for a subdomain that you choose, which masks click and open-tracking links to your domain rather than a SendGrid domain. This increases deliverability, builds trust, and strengthens your brand in your emails.

{% anchor h2 %}
What is IP whitelabeling?
{% endanchor %}

[IP whitelabeling]({{root_url}}/User_Guide/Settings/Whitelabel/ips.html) adds an A-record on a subdomain that points directly to your unique sending IP address. This further increases trust and improves deliverability of your email.

{% anchor h2 %}
How do I whitelabel?
{% endanchor %}

Each whitelabel type is a two-step process: 

1. SendGrid will generate DNS records that you must add to your domain host (GoDaddy, Network Solutions, Hover, etc.). 
2. Click the gear icon in-line with your domain name on the main whitelabel page, then select “validate” in the dropdown list to initiate a check that ensures the records on your DNS host match the records SendGrid generated.

{% anchor h2 %}
Can I whitelabel multiple domains?
{% endanchor %}

Yes, it's possible to whitelabel multiple domains using the improved whitelabel management process. When multiple whitelabel domains exist on your account, SendGrid will use the from address for each email you send through SendGrid and match it to a domain and link whitelabel. If the from address does not match an existing whitelabel, SendGrid will fall back to the whitelabel you have chosen as the default.