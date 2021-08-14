---
title: Tabella Locations in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.
ms.openlocfilehash: 887c9c7198272fa2087399c0ccf67e37ae890dc90a322eb17bcff16688808080
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343230"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabella Locations in Skype for Business Server 2015
 
Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**Posizione** <br/> |nvarchar(max)  <br/> ||Posizione della chiamata di emergenza.  <br/> |
   

