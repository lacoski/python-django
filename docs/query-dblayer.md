Use get object or 404() for Single Objects

Be Careful With Queries That Might Throw
Exceptions
```py
from django.core.exceptions import ObjectDoesNotExist
from flavors.models import Flavor
from store.exceptions import OutOfStock
def list_flavor_line_item(sku):
  try:
    return Flavor.objects.get(sku=sku, quantity__gt=0)
  except Flavor.DoesNotExist:
    msg = "We are out of {0}".format(sku)
  raise OutOfStock(msg)

def list_any_line_item(model, sku):
  try:
    return model.objects.get(sku=sku, quantity__gt=0)
  except ObjectDoesNotExist:
    msg = "We are out of {0}".format(sku)
  raise OutOfStock(msg)
```

query may return more than one object
- check for a MultipleObjectsReturned exception

```py
def list_flavor_line_item(sku):
try:
  return Flavor.objects.get(sku=sku, quantity__gt=0)
except Flavor.DoesNotExist:
  msg = "We are out of {}".format(sku)
  raise OutOfStock(msg)
except Flavor.MultipleObjectsReturned:
  msg = "Multiple items have SKU {}. Please fix!".format(sku)
  raise CorruptedDatabase(msg)
```

Query Expressions

Sử dụng cú pháp hỗ trợ bảo django
```
customers = Customer.objects.filter(scoops_ordered__gt=F('store_visits'))
```
