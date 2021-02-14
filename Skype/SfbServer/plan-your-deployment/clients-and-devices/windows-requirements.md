---
title: Requisiti client Windows e supporto software
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
description: 'Riepilogo: esaminare i requisiti di supporto dei client Windows durante la pianificazione di Skype for Business Server.'
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816066"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisiti client Windows e supporto software
 
**Riepilogo:** Esaminare i requisiti di supporto dei client Windows durante la pianificazione di Skype for Business Server.
  
Questa sezione riepiloga il software necessario per supportare i client Windows Skype for Business. Questi client vengono installati durante l'installazione di Microsoft 365 o Office 365 e sono disponibili anche in [Scarica Skype for Business in tutti i dispositivi.](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Il componente aggiuntivo per riunioni online per Skype for Business, che supporta la gestione delle riunioni dal client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Skype for Business. 
  
**Software necessario per il client Skype for Business e il componente aggiuntivo per riunioni online**

|**Componente del sistema**|**Versioni supportate**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 o versione successiva con service pack più recente  <br/> **Nota:** Skype for Business e il componente aggiuntivo per riunioni online per Skype for Business non sono supportati in Windows Vista o Windows XP (qualsiasi versione). <br/> |
|Installazione e aggiornamenti  <br/> |Diritti e autorizzazioni di amministratore  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Browser Internet Explorer 11  <br/>  Browser Internet Explorer 10 <br/> Browser Internet Explorer 9  <br/> Browser Internet Explorer 8  <br/> Browser Internet Explorer 7  <br/> Mozilla Firefox  <br/>  Web browser Google Chrome  <br/>**Nota:** Se si usa Skype for Business con Microsoft Exchange Online e l'organizzazione ha distribuito un proxy HTTP di autenticazione, è necessario Internet Explorer 8 o versione successiva.           |
|Integrazione di Microsoft Office  <br/> | Outlook 2010 o versioni successive |
|Integrazione di Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o versione successiva  | 
   
## <a name="hardware"></a>Hardware

Fare riferimento ai requisiti di Microsoft 365 e Office [System](https://products.office.com/office-system-requirements) per l'hardware necessario per eseguire il client Skype for Business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>App Riunioni Skype e Skype for Business Web App 

L'app Riunioni Skype e Skype for Business Web App supportano combinazioni specifiche di sistemi operativi e browser. Per informazioni dettagliate, vedere [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilizzo dei profili obbligatori

Se si prevede di usare le funzionalità di conferenza di Skype for Business, evitare di usare i profili obbligatori di Servizi di dominio Active Directory per accedere al client Skype for Business. Poiché i profili obbligatori sono profili utente di sola lettura, le chiavi dell'infrastruttura a chiave pubblica (PKI) necessarie per le conferenze Skype for Business non possono essere salvate nel profilo. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisiti di sistema per Skype for Business per Windows Phone
 
 
Microsoft Skype for Business per Windows Phone offre messaggistica istantanea, presenza avanzata e telefonia per gli utenti dell'organizzazione che si connettono da uno smartphone o da un dispositivo mobile Windows Professional. I dispositivi mobili consentono agli utenti di estendere la copertura di Skype for Business. In questo argomento vengono descritte le considerazioni sulla pianificazione per Skype for Business per Windows Phone che includono l'identificazione dei prerequisiti e dei requisiti tecnici, dei componenti necessari e delle linee guida per la distribuzione.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Prerequisiti di Skype for Business per Windows Phone

Di seguito sono riportati i prerequisiti di Skype for Business per Windows Phone.
  
- Windows Phone 8.1 o versione successiva.
    
- Il dispositivo Windows Phone deve avere gli aggiornamenti più recenti disponibili da Microsoft. Per informazioni dettagliate, vedi la sezione relativa a Windows Phone 8.1 nella [cronologia degli aggiornamenti di Windows Phone 8.](https://go.microsoft.com/fwlink/p/?LinkID=281961)
    
- Il dispositivo deve disporre di 22 MB di spazio su disco disponibile.
    
- L'utente deve disporre di un piano voce e dati di un gestore telefonico.


## <a name="see-also"></a>Vedere anche

[Pianificare i client riunioni (app Web e app Riunioni)](meetings-clients.md)
  
[Requisiti del client Skype for Business su Mac](mac-requirements.md)

[Scaricare Skype for Business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Requisiti di sistema di Microsoft 365 e Office](https://products.office.com/office-system-requirements)
