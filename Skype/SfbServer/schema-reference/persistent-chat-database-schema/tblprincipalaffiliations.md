---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194670"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|principalID  <br/> |int, not null  <br/> |ID dell'oggetto Principal affiliato.  <br/> |
|affiliationID  <br/> |int, not null  <br/> |ID dell'entità che rappresenta l'affiliazione. Ogni entità (ad eccezione di System-User-Types) ha anche una propria affiliazione.  <br/> |
|Indice  <br/> |int, not null  <br/> |Indice. Il valore di self-Affiliations è-1 e per le altre affiliazioni aumenta sequenzialmente da 1 all'interno di ogni \<PrincipalId, affiliationId\> bucket.  <br/> |
|updatedBy  <br/> |int, not null  <br/> |Principal che ha eseguito l'aggiornamento più recente. Si tratta in genere di 1, che indica la sincronizzazione di Active Directory.  <br/> |
   
**Tasti**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Chiave primaria.  <br/> |
|principalID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
|affiliationID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
   

