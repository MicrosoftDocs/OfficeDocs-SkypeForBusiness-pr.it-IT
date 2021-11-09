---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.
ms.openlocfilehash: d28b81d6ce0169999297dbcde65b1d7fbde38780
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854070"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), not null  <br/> |URI (Uniform Resource Identifier) del canale.  <br/> |
|userId  <br/> |int, not null  <br/> |ID dell'entità del partecipante (corrispondente alla tabella tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, not null  <br/> |Timestamp dell'evento di partecipazione.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null se il partecipante sta ancora partecipando. Timestamp dell'evento di uscita dal canale, se not null.  <br/> Queste voci vengono rimosse alle fine quando tutti i convertitori hanno elaborato l'evento.  <br/> |
|userUri  <br/> |nvarchar (255), not null  <br/> |URI dell'utente.  <br/> |
|serverID  <br/> |int  <br/> |Identità del server (come nella tabella tblServerIdentity.serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Sessione del server. Numero casuale generato a ogni avvio di un servizio chat, utilizzato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Chiave primaria.  <br/> |
   

