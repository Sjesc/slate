---
title: Referencia API Facturacion Digital

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - csharp
  - python
  - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentacion para API Facturacion Digital
---

# Introduccion

Bienvenido al API de Facturacion Digital! ...

# Autenticacion

> Para autenticarte, usa este codigo:

```csharp
using Unidigital.DigitalInvoice.ApiClient;

var api = DigitalInvoiceClient.Authorize("usario", "contraseña")
```

```python
import unidigital.digitalinvoice

api = digitalinvoice.authorize('usuario', 'contraseña')
```

```shell
curl "www.unidigital.global/digitalinvoiceservice/user/login" \
  -H 'Content-Type: application/json' \
  -d '{"UserName":"usuario","Password":"contraseña"}'
```

```javascript
const digitalInvoice = require('unidigital/digitalinvoice');

let api = digitalInvoice.authorize("usuario", "contraseña");
```

> Asegurate de reemplazar `usuario` y `contraseña` con tus credenciales.

...

<aside class="notice">
...
</aside>

# Batch

## Abrir batch

```csharp
using Unidigital.DigitalInvoice.ApiClient;

var api = DigitalInvoiceClient.Authorize("usario", "contraseña")

var batch = api.OpenBatch("SerieId")
```

```python
import unidigital.digitalinvoice

api = digitalinvoice.authorize('usuario', 'contraseña')
batch = api.open_batch("serieid")
```

```shell
curl "www.unidigital.global/digitalinvoiceservice/batch/open" \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {token}' \
  -d '{"SeriesStrongId":"serieid"}'
```

```javascript
const digitalInvoice = require('unidigital/digitalinvoice');

let api = digitalInvoice.authorize("usuario", "contraseña");

let batch = api.openBatch("serieid")
```

> El comando de arriba regresa un JSON estructurado de la siguiente forma:

```json
{
    "result": { 
        "StrongId": "..." 
    },
    "hasErrors": false,
    "errors": []
}
```

Este endpoint crea un batch y le asigna el estatus de "Abierto"

### Peticion HTTP

`POST www.unidigital.global/digitalinvoiceservice/batch/open`

### Estructura del cuerpo

Campo | Valor por defecto | Descripcion
--------- | ------- | -----------
SerieStrongId | NA | Id de la serie

<aside class="success">
Debes estar autenticado para realizar esta peticion
</aside>

