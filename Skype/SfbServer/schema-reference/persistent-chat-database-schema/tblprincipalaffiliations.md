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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814474"
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
   

