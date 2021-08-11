---
title: Monitorare, avviare e arrestare i servizi Persistent Chat in Skype for Business Server 2015
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
description: 'Riepilogo: informazioni su come avviare, arrestare e monitorare i servizi Persistent Chat in Skype for Business Server 2015.'
ms.openlocfilehash: c541964659ceec36209c4ea262d047cf116c35e444354f6e450b7b684e4992ec
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590720"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Monitorare, avviare e arrestare i servizi Persistent Chat in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come avviare, arrestare e monitorare i servizi di Persistent Chat in Skype for Business Server 2015.
  
I servizi Chat persistente e Conformità chat persistente fanno parte della topologia di Skype for Business Server e possono pertanto essere monitorati, arrestati e avviati utilizzando i cmdlet seguenti:
  
|Cmdlet|Funzione|
|:-----|:-----|
|get-CsWindowsService  <br/> |Restituisce informazioni dettagliate sui Skype for Business Server 2015 eseguiti come Windows servizi.  <br/> |
|start-CsWindowsService  <br/> |Avvia il servizio.  <br/> |
|stop-CsWindowsService  <br/> |Arresta il servizio.  <br/> |
   
> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare Persistent Chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 

Per informazioni dettagliate su come utilizzare i cmdlet, vedere [Skype for Business Server 2015 Management Shell.](../management-shell.md)
  

