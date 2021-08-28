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
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso a Servizi di dominio Active Directory).
ms.openlocfilehash: 3869107cf98251100ec7fa483bc403e1c19239a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622068"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso a Servizi di dominio Active Directory).
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|affDescription  <br/> |nvarchar (256), not null  <br/> |Stringa che identifica l'affiliazione.  <br/> Il formato è: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha aggiornato la riga. È sempre uguale a 1 (utente di sistema) perché la sincronizzazione di Active Directory è l'unica origine per queste voci.  <br/> |
   
**Tasti**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
   

