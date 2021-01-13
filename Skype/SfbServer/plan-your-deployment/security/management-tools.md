---
title: Strumenti di gestione di Windows PowerShell e Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'In Skype for Business Server, gli strumenti di gestione vengono implementati tramite Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Gli strumenti di Skype for Business Server implementati tramite Windows PowerShell includono quanto segue:'
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832156"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Strumenti di gestione di Windows PowerShell e Skype for Business Server
 
In Skype for Business Server, gli strumenti di gestione vengono implementati tramite Windows PowerShell. Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Gli strumenti di Skype for Business Server implementati tramite Windows PowerShell includono quanto segue: 
  
- **Generatore di topologie**. Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie e convalidare la topologia prima di iniziare le installazioni del server. Quando si installa Skype for Business Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il server viene distribuito come indicato nella topologia. Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server. I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologie.
    
- **Skype for Business Server Management Shell**. È possibile utilizzare Skype for Business Server Management Shell per la gestione completa della riga di comando della distribuzione.
    
- **Pannello di controllo di Skype for Business Server**. È possibile utilizzare l'interfaccia utente del pannello di controllo di Skype for Business Server per gestire le attività più comuni nella distribuzione.
    
Questi strumenti utilizzano i cmdlet di Windows PowerShell per la gestione della distribuzione, inclusi quasi 550 cmdlet specifici del prodotto. I cmdlet di sicurezza inclusi in Skype for Business Server vengono utilizzati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni. È disponibile un'ampia gamma di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per l'autenticazione tramite certificato e PIN. Inoltre, un certo numero di cmdlet consentono di utilizzare la nuova funzionalità di controllo di accesso Role-Based (RBAC) per delegare il controllo amministrativo di Skype for Business Server. Per informazioni dettagliate sui cmdlet di Skype for Business Server, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md).
  
Le funzionalità per la sicurezza degli script per Windows PowerShell sono progettate appositamente per evitare alcuni dei problemi di sicurezza correlati agli script di tecnologie meno recenti, incluso Microsoft Visual Basic Scripting Edition (VBScript). Le funzionalità di sicurezza di Windows PowerShell sono pensate per creare un ambiente in cui gli utenti non possono eseguire gli script facilmente o in modo inconsapevole. Le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita. È possibile modificare lo stato di queste funzionalità per adattarle alle esigenze specifiche per gli script e a un'ampia gamma di obiettivi per la sicurezza. Ciò non significa che l'esecuzione degli script sia resa impossibile dalla shell. L'obiettivo, per impostazione predefinita, è invece quello di rendere difficile per gli utenti eseguire script senza esserne consapevoli. Per ulteriori informazioni, vedere [sicurezza degli script di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=213145).
  

