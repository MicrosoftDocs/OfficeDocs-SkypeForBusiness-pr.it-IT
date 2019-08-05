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
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene i partecipanti correnti per canale e per server.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194693"
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
   

