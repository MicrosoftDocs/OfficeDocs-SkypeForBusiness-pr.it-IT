---
title: Monitorare, avviare e arrestare i servizi di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 846d7376e1a3e9bd06ae74c20ee0812c8c78bbeb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817475"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorare, avviare e arrestare i servizi di Chat persistente
 
**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di chat persistenti in Skype for Business Server 2015.
  
I servizi di chat persistenti e i servizi di conformità della chat persistente fanno parte della topologia di Skype for Business Server e possono quindi essere monitorati, fermati e avviati usando i seguenti cmdlet:
  
|||
|:-----|:-----|
|Get-CsWindowsService  <br/> |Restituisce informazioni dettagliate sui componenti di Skype for Business Server 2015 che vengono eseguiti come servizi Windows.  <br/> |
|Start-CsWindowsService  <br/> |Avvia il servizio.  <br/> |
|Stop-CsWindowsService  <br/> |Arresta il servizio.  <br/> |
   
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

Per informazioni dettagliate su come usare i cmdlet, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

