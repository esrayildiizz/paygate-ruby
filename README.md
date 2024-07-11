

  
<p align="center">
  <img src="https://github.com/esrayildiizz/Example/assets/106755194/e0197438-b265-449a-a90b-cf4f526a0e01" alt="PAYGATE Image"/>
</p>

<p align="center">
<strong>PAYGATE</strong>
</p>

<p align="center">
PayGate ile tüm online ödemelerinizi tek merkezden yönetin 
</p>
<p align="center">
katma değerli servislerimiz ile ödeme giderlerinizi azaltın, cironuzu artırın ve işletmenizi büyütün.
</p>

## PAYGATE
[![Craftgate Dotnet CI](https://img.shields.io/badge/Craftgate%20Dotnet%20CI-passing-brightgreen)]()
[![nuget](https://img.shields.io/badge/nuget-v1.0.61-blue)]()
[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)]()


## Requirements
- .NET Framework 4.6+
- .NET Core 1.1+
- .NET Core 2.0+

## Installation
`Install-Package  ...... `



## Usage
PayGate API'sine erişmek için öncelikle API kimlik bilgilerini (örneğin bir API anahtarı ve gizli anahtar) edinmeniz gerekir. Zaten bir Craftgate hesabınız yoksa https://paygate.io/ adresinden kaydolabilirsiniz.

API kimlik bilgilerinizi aldıktan sonra, PayGate kimlik bilgilerinizle bir örnek oluşturarak PayGate'i kullanmaya başlayabilirsiniz.


`PayGateClient _paygate = new PayGateClient("<YOUR API KEY>", "<YOUR SECRET KEY>");`


Varsayılan olarak PayGate istemcisi üretim API sunucularına bağlanır https://api.paygate.io. Test amaçlı olarak lütfen https://sandbox-api.paygate.io. kullanarak deneme alanı URL'sini kullanın.


`PayGateClient _paygate = new PayGateClient("<YOUR API KEY>", "<YOUR SECRET KEY>", "https://sandbox-api.paygate.io");`


## Examples


### Running the Examples


### Credit Card Payment Use Case

```ruby
require 'craftgate'

craftgate = Craftgate::Client.new(api_key: '<YOUR API KEY>', secret_key: '<YOUR SECRET KEY>')

request = {
  price: 100.0,
  paid_price: 100.0,
  wallet_price: 0.0,
  installment: 1,
  conversation_id: '456d1297-908e-4bd6-a13b-4be31a6e47d5',
  currency: Craftgate::Model::Currency::TRY,
  payment_group: Craftgate::Model::PaymentGroup::LISTING_OR_SUBSCRIPTION,
  card: {
    card_holder_name: 'Haluk Demir',
    card_number: '5258640000000001',
    expire_year: '2044',
    expire_month: '07',
    cvc: '000'
  },
  items: [
    {
      name: 'Item 1',
      price: 30.0,
      external_id: 'externalId-1'
    },
    {
      name: 'Item 2',
      price: 50.0
    },
    {
      name: 'Item 3',
      price: 20.0,
      external_id: 'externalId-3'
    }
  ]
}

response = craftgate.payment.create_payment(request)
raise 'Response is null' if response.nil?
```

### Contributions
*For all contributions to this client please see the contribution guide here.*

## License

**MIT**










