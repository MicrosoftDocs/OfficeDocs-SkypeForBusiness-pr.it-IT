---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso a servizi di dominio Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831426"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso a servizi di dominio Active Directory).
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|affDescription  <br/> |nvarchar (256), not null  <br/> |Stringa che identifica l'affiliazione.  <br/> Il formato è: GUID:  _{0}_ URI: _{1}_> ID:  _{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha aggiornato la riga. È sempre uguale a 1 (utente di sistema) perché la sincronizzazione di Active Directory è l'unica origine per queste voci.  <br/> |
   
**Chiavi**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
   

