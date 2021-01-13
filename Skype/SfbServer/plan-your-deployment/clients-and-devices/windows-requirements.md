---
title: Requisiti del client Windows e supporto software
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Riepilogo: esaminare i requisiti del supporto client di Windows durante la pianificazione di Skype for Business Server.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816066"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisiti del client Windows e supporto software
 
**Riepilogo:** Esaminare i requisiti del supporto client di Windows durante la pianificazione di Skype for Business Server.
  
In questa sezione viene riepilogato il software necessario per supportare i client Windows Skype for business. Questi client vengono installati quando si installa Microsoft 365 o Office 365 e sono disponibili anche [per il download di Skype for business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Il componente aggiuntivo per riunioni online per Skype for business, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Skype for business. 
  
**Software necessario per il client Skype for business e il componente aggiuntivo per riunioni online**

|**Componente del sistema**|**Versioni supportate**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 o versione successiva con il Service Pack più recente  <br/> **Nota:** Skype for business e il componente aggiuntivo per riunioni online per Skype for business non sono supportati in Windows Vista o Windows XP (qualsiasi versione). <br/> |
|Installazione e aggiornamenti  <br/> |Diritti e autorizzazioni di amministratore  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet browser  <br/>  Internet Explorer 10 (browser Internet) <br/> Internet Explorer 9 (browser Internet)  <br/> Internet Explorer 8 browser Internet  <br/> Internet Explorer 7 Internet browser  <br/> Mozilla Firefox  <br/>  Web browser di Google Chrome  <br/>**Nota:** Se si utilizza Skype for business con Microsoft Exchange Online e l'organizzazione ha distribuito un proxy HTTP di autenticazione, è necessario Internet Explorer 8 o versione successiva.           |
|Integrazione di Microsoft Office  <br/> | Outlook 2010 o versioni successive |
|Integrazione di Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o versioni successive  | 
   
## <a name="hardware"></a>Hardware

Fare riferimento ai requisiti di Microsoft 365 e Office [System](https://products.office.com/office-system-requirements) per l'hardware necessario per eseguire il client Skype for business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>App per riunioni Skype e Skype for Business Web App 

L'app Skype Meetings e Skype for business web app supportano specifiche combinazioni di sistemi operativi e browser. Per ulteriori informazioni, vedere [Plan for meetings clients (Web App and Meetings app)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilizzo dei profili obbligatori

Se si prevede di utilizzare le funzionalità di conferenza di Skype for business, evitare di usare i profili obbligatori di servizi di dominio Active Directory per accedere al client Skype for business. Poiché i profili obbligatori sono profili utente di sola lettura, le chiavi dell'infrastruttura a chiave pubblica (PKI) richieste per le conferenze di Skype for business non possono essere salvate nel profilo. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisiti di sistema per Skype for business per Windows Phone
 
 
Microsoft Skype for business per Windows Phone fornisce messaggistica istantanea, presenza avanzata e telefonia per gli utenti dell'organizzazione che si connettono da uno smartphone o da un dispositivo mobile Windows Professional. I dispositivi mobili consentono agli utenti di estendere la portata di Skype for business. In questo argomento vengono descritte le considerazioni sulla pianificazione di Skype for business per Windows Phone che includono i prerequisiti e i requisiti tecnici, i componenti necessari e le linee guida per la distribuzione.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Prerequisiti di Skype for business per Windows Phone

Di seguito sono riportati i prerequisiti di Skype for business per Windows Phone.
  
- Windows Phone 8,1 o versione successiva.
    
- Il dispositivo Windows Phone deve disporre degli aggiornamenti più recenti disponibili da Microsoft. Per informazioni dettagliate, vedere la sezione Windows Phone 8,1 nella [cronologia degli aggiornamenti di Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Il dispositivo deve disporre di 22 MB di spazio disponibile su disco.
    
- L'utente deve disporre di un piano voce e dati di un gestore telefonico.


## <a name="see-also"></a>Vedere anche

[Pianificare i client di riunioni (app per le riunioni e le app Web)](meetings-clients.md)
  
[Requisiti client Skype for business su Mac](mac-requirements.md)

[Scaricare Skype for business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisiti di Microsoft 365 e Office System](https://products.office.com/office-system-requirements)
