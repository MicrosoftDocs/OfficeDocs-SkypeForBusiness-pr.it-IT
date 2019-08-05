---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194663"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinAffiliationsDirty  <br/> |bit, not null  <br/> |True se le affiliazioni principali devono essere aggiornate.  <br/> |
|prinAttributesDirty  <br/> |bit, not null  <br/> |True se gli attributi Principal devono essere aggiornati.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True se l'entità è stata eliminata.  <br/> |
|tryCount  <br/> |int  <br/> |Numero di tentativi di aggiornare l'oggetto Principal da servizi di dominio Active Directory che si sono verificati finora.  <br/> |
|lastTry  <br/> |DateTime  <br/> |Indicatore di data e ora dal tentativo più recente di aggiornare l'entità. Può essere null se non è ancora stato tentato l'aggiornamento.  <br/> |
|nextTry  <br/> |DateTime  <br/> |Indicatore di data e ora per il successivo aggiornamento programmato. Può essere null se non è stato programmato un ulteriore aggiornamento.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|prinID  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
   

