customer = gateway.customer.find("the_customer_id")
customer.payment_methods # array of braintree.PaymentMethod instances
payment_method.default
payment_method = gateway.payment_method.find("credit-card-token")
payment_method.__class__
# <class 'braintree.credit_card.CreditCard'>

payment_method = gateway.payment_method.find("paypal-account-token")
payment_method.__class__
# <class 'braintree.paypal_account.PayPalAccount'>

payment_method = gateway.payment_method.find("apple-pay-token")
payment_method.__class__
# <class 'braintree.apple_pay_card.ApplePayCard'>

payment_method = gateway.payment_method.find("android-pay-token")
payment_method.__class__
# <class 'braintree.android_pay_card.AndroidPayCard'>
