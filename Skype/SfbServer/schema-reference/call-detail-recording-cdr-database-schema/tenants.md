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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194732"
---
# <a name="tenants-table"></a>Tabella Tenants
 
La tabella Tenants è una tabella di supporto in cui è archiviato un elenco dei diversi tenant. Ogni record nella tabella rappresenta un tenant.
  
> [!NOTE]
> Nella distribuzione locale, CDR usa l'ID tenant di build-in per indicare il tipo di autenticazione diverso, ad esempio la connettività di messaggistica istantanea pubblica, federati e Anonymous. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ID tenant** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo ID tenant.  <br/> |
|**TenantKey** <br/> |nvarchar (256)  <br/> || Valori consentiti: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-federati <br/>  00000000-0000-0000-0000-000000000002-Anonimo <br/>  00000000-0000-0000-0000-000000000003-connettività per messaggistica istantanea pubblica <br/> |
   

