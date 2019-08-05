---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194651"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, non null  <br/> |GUID del componente aggiuntivo.  <br/> |
|siopName  <br/> |nvarchar (50), not null  <br/> |Nome visualizzato del componente aggiuntivo.  <br/> |
|siopUrl  <br/> |nvarchar (255), not null  <br/> |URL del componente aggiuntivo.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|siopID  <br/> |Chiave primaria.  <br/> |
   

