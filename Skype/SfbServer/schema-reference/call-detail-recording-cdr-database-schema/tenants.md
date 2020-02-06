---
title: Tabella Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814854"
---
# <a name="tenants-table"></a>Tabella Tenants
 
La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
  
> [!NOTE]
> Nella distribuzione locale, CDR usa l'ID tenant di build-in per indicare il tipo di autenticazione diverso, ad esempio la connettività di messaggistica istantanea pubblica, federati e Anonymous. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ID tenant** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo ID tenant.  <br/> |
|**TenantKey** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-federati <br/>  00000000-0000-0000-0000-000000000002-Anonimo <br/>  00000000-0000-0000-0000-000000000003-connettività per messaggistica istantanea pubblica <br/> |
   

