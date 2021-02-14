---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze ai percorsi, inclusi i gruppi di sicurezza di Servizi di dominio Active Directory, nei contenitori di Active Directory e nei domini.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815866"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze ai percorsi, inclusi i gruppi di sicurezza di Servizi di dominio Active Directory, nei contenitori di Active Directory e nei domini.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|principalID  <br/> |int, not null  <br/> |ID dell'entità affiliata.  <br/> |
|affiliationID  <br/> |int, not null  <br/> |ID dell'entità che rappresenta l'affiliazione. Ogni entità prevede anche un'auto-affiliazione (eccetto system-user-types).  <br/> |
|index  <br/> |int, not null  <br/> |Indice. Il valore per le auto-affiliazioni è -1 e per le altre affiliazioni aumenta in sequenza da 1 all'interno di ogni \<principalID, affiliationId\> contenitore.  <br/> |
|updatedBy  <br/> |int, not null  <br/> |Entità che ha effettuato l'ultimo aggiornamento. Viene utilizzato in genere il valore 1, che indica la sincronizzazione di Active Directory.  <br/> |
   
**Tasti**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Chiave primaria.  <br/> |
|principalID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
   

