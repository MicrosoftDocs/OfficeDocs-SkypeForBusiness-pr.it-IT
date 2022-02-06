---
title: Tabella Tenant
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui viene archiviato un elenco dei diversi tenant. Ogni record della tabella rappresenta un tenant.
---

# <a name="tenants-table"></a>Tabella Tenant
 
La tabella Tenants è una tabella di supporto in cui viene archiviato un elenco dei diversi tenant. Ogni record della tabella rappresenta un tenant.
  
> [!NOTE]
> Nelle distribuzioni on-premise, registrazione dettagli chiamata utilizza l'ID tenant predefinito per indicare tipi di autenticazione diversi, come connettività per messaggistica istantanea pubblica, autenticazione federata e autenticazione anonima. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo ID tenant.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valori consentiti: <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Federato <br/>  00000000-0000-0000-0000-000000000002 - Anonimo <br/>  00000000-0000-0000-0000-000000000003 - Connettività per messaggistica istantanea pubblica <br/> |
   

