---
title: Strumenti di gestione di Windows PowerShell e Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'In Skype for Business Server gli strumenti di gestione vengono implementati con Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di scripting completo. Gli strumenti di Skype for Business Server implementati con Windows PowerShell includono i seguenti:'
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194887"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Strumenti di gestione di Windows PowerShell e Skype for Business Server
 
In Skype for Business Server gli strumenti di gestione vengono implementati con Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di scripting completo. Gli strumenti di Skype for Business Server implementati con Windows PowerShell includono i seguenti: 
  
- **Generatore**di topologie. Puoi usare generatore di topologia per creare, modificare e pubblicare la topologia pianificata e convalidare la topologia prima di iniziare le installazioni del server. Quando si installa Skype for Business Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il programma di installazione distribuisce il server come indicato nella topologia. Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server. I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologia.
    
- **Skype for Business Server Management Shell**. È possibile usare Skype for Business Server Management Shell per la gestione completa della riga di comando della distribuzione.
    
- **Pannello di controllo di Skype for Business Server**. È possibile usare l'interfaccia utente del pannello di controllo di Skype for Business Server per gestire le attività più comuni nella distribuzione.
    
Questi strumenti usano i cmdlet di Windows PowerShell per la gestione della distribuzione, tra cui quasi tutti i cmdlet specifici per il prodotto 550. I cmdlet di sicurezza inclusi in Skype for Business Server vengono usati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni. È disponibile un'ampia varietà di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per il certificato e l'autenticazione PIN (Personal Identification Number). Inoltre, un certo numero di cmdlet consente di usare la nuova funzionalità controllo di accesso basato sui ruoli (RBAC) per delegare il controllo amministrativo di Skype for Business Server. Per informazioni dettagliate sui cmdlet di Skype for Business Server, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md).
  
Le funzionalità di sicurezza degli script per Windows PowerShell sono progettate in modo specifico per evitare alcuni problemi di sicurezza correlati agli script delle tecnologie meno recenti, tra cui Microsoft Visual Basic Scripting Edition (VBScript). Le caratteristiche di sicurezza di Windows PowerShell sono destinate a creare un ambiente in cui gli utenti non possono eseguire facilmente o in modo inconsapevolmente gli script. Per impostazione predefinita, le caratteristiche di sicurezza di Windows PowerShell sono abilitate. Puoi modificare lo stato di queste funzionalità per soddisfare le tue esigenze di scripting e diversi obiettivi di sicurezza. Questo non significa che la Shell rende impossibile l'esecuzione di script da parte degli utenti. La Shell rende invece difficile, per impostazione predefinita, che gli utenti eseguano gli script senza rendersene conto. Per informazioni dettagliate, vedere [sicurezza degli script di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

