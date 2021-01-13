---
title: Monitorare, avviare e arrestare i servizi di chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814136"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorare, avviare e arrestare i servizi di chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di chat persistente in Skype for Business Server 2015.
  
I servizi di chat persistente e i servizi di conformità di Persistent Chat fanno parte della topologia di Skype for Business Server e pertanto possono essere monitorati, interrotti e avviati utilizzando i cmdlet seguenti:
  
|||
|:-----|:-----|
|Get-CsWindowsService  <br/> |Restituisce informazioni dettagliate sui componenti di Skype for Business Server 2015 che vengono eseguiti come servizi di Windows.  <br/> |
|Start-CsWindowsService  <br/> |Avvia il servizio.  <br/> |
|Stop-CsWindowsService  <br/> |Interrompe il servizio.  <br/> |
   
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

Per informazioni dettagliate su come utilizzare i cmdlet, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

