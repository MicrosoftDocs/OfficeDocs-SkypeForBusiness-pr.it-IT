---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene i partecipanti correnti per canale e per server.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814644"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contiene i partecipanti correnti per canale e per server.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), not null  <br/> |URI (Uniform Resource Identifier) del canale.  <br/> |
|userId  <br/> |int, not null  <br/> |ID principale del partecipante (corrispondente alla tabella tblPrincipal. prinID).  <br/> |
|joinedAt  <br/> |bigint e non null  <br/> |Indicatore di data e ora dell'evento Joining.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null se i partecipanti sono ancora Uniti. L'indicatore di data e ora del canale che lascia l'evento se non è null.  <br/> Queste voci vengono infine rimosse quando tutti i traduttori elaborano l'evento.  <br/> |
|userUri  <br/> |nvarchar (255), not null  <br/> |URI utente.  <br/> |
|serverID  <br/> |int  <br/> |Identità del server (come nella tabella tblServerIdentity. serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sessione del server. Si tratta di un numero casuale generato ogni volta che viene avviato un servizio chat. Viene usato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Chiave primaria.  <br/> |
   

