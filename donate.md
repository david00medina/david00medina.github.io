---
layout: page
title: Donate
permalink: /donate/
---

<ul class="features">
    <li>
        <a class="paypal-subscribe" href="https://www.paypal.com/webapps/billing/plans/subscribe?plan_id=P-6SP66253NK602924TMV2TXHI">
            <h3 id="paypal"><object data="/assets/css/images/paypal.svg" height="32px"></object>  PayPal</h3>
        </a>
    </li>
    <li>
        <a class="buy-me-a-coffee" href="https://www.buymeacoffee.com/sharvik">
            <h3 id="buymeacoffee"><object data="/assets/css/images/coffee.svg" height="32px"></object>  Buy me a coffee</h3>
        </a>
    </li>
</ul>
<div id="paypal-button-container-P-6SP66253NK602924TMV2TXHI"></div>
<script src="https://www.paypal.com/sdk/js?client-id=AXA4r5NRqvr3u-ErskBtF9wdEQMQF6HNGwgCeOJlCNV4mGzX9he-HiRLmDjO7yuHq8saxOCqoYfURO4r&vault=true&intent=subscription" data-sdk-integration-source="button-factory"></script>
<script>
  paypal.Buttons({
      style: {
          shape: 'pill',
          color: 'gold',
          layout: 'horizontal',
          label: 'subscribe'
      },
      createSubscription: function(data, actions) {
        return actions.subscription.create({
          /* Creates the subscription */
          plan_id: 'P-6SP66253NK602924TMV2TXHI'
        });
      },
      onApprove: function(data, actions) {
        alert(data.subscriptionID); // You can add optional success message for the subscriber here
      }
  }).render('#paypal-button-container-P-6SP66253NK602924TMV2TXHI'); // Renders the PayPal button
</script>