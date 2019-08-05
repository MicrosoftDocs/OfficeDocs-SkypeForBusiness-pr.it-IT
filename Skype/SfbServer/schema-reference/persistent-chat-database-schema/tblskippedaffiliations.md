---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso ai servizi di dominio Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194648"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso ai servizi di dominio Active Directory).
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|affDescription  <br/> |nvarchar (256), not null  <br/> |Stringa che identifica l'affiliazione.  <br/> Il formato è: GUID: _{0}_ uri: _{1}_> ID:_{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha aggiornato la riga. È sempre 1 (utente di sistema) perché Active Directory Sync è l'unica fonte per queste voci.  <br/> |
   
**Tasti**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
   

