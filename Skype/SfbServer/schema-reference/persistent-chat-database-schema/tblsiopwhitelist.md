---
title: tblSiopWhiteList
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
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
ms.openlocfilehash: 78cc98f584f20d3a08e9ed750ed9ac406f7e5780
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613826"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, not null  <br/> |GUID del componente aggiuntivo.  <br/> |
|siopName  <br/> |nvarchar (50), not null  <br/> |Nome visualizzato del componente aggiuntivo.  <br/> |
|siopUrl  <br/> |nvarchar (255), not null  <br/> |URL del componente aggiuntivo.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|siopID  <br/> |Chiave primaria.  <br/> |
   

