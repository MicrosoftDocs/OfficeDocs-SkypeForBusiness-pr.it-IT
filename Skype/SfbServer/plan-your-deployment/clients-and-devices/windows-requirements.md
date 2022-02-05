---
title: Windows client e supporto software
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Riepilogo: esaminare i requisiti di supporto Windows client durante la pianificazione Skype for Business Server.'
---

# <a name="windows-client-requirements-and-software-support"></a>Windows client e supporto software
 
**Riepilogo:** Esaminare i requisiti Windows supporto client durante la pianificazione Skype for Business Server.
  
In questa sezione viene riepilogato il software necessario per supportare i Skype for Business Windows client. Questi client vengono installati quando Microsoft 365 o Office 365 e sono disponibili anche in [Download Skype for Business su tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Il componente aggiuntivo per riunioni online per Skype for Business, che supporta la gestione delle riunioni dal client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Skype for Business. 
  
**Software necessario per Skype for Business client e il componente aggiuntivo per riunioni online**

|**Componente del sistema**|**Versioni supportate**|
|:-----|:-----|
|Windows sistema operativo  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 o versione successiva con service pack più recente  <br/> **Nota:** Skype for Business e il componente aggiuntivo per riunioni online per Skype for Business non sono supportati in Windows Vista o Windows XP (qualsiasi versione). <br/> |
|Installazione e aggiornamenti  <br/> |Diritti e autorizzazioni di amministratore  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Browser Internet Explorer 11  <br/>  Internet Explorer 10 Browser Internet <br/> Browser Internet Explorer 9  <br/> Browser Internet Explorer 8  <br/> Browser Internet Explorer 7  <br/> Mozilla Firefox  <br/>  Browser Web Google Chrome  <br/>**Nota:** Se si usa Skype for Business con Microsoft Exchange Online e l'organizzazione ha distribuito un proxy HTTP di autenticazione, è necessario Internet Explorer 8 o versione successiva.           |
|Integrazione di Microsoft Office  <br/> | Outlook 2010 o versioni successive |
|Integrazione di Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o versione successiva  | 
   
## <a name="hardware"></a>Hardware

Fare riferimento ai Microsoft 365 e Office [di](https://products.office.com/office-system-requirements) sistema per l'hardware necessario per eseguire il client Skype for Business client.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype riunioni e Skype for Business Web App 

L Skype e l'app Riunioni Skype for Business Web App supportano combinazioni specifiche di sistemi operativi e browser. Per informazioni dettagliate, vedere [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Utilizzo dei profili obbligatori

Se si prevede di utilizzare le funzionalità di conferenza Skype for Business, evitare di utilizzare i profili obbligatori di Servizi di dominio Active Directory per accedere al client Skype for Business. Poiché i profili obbligatori sono profili utente di sola lettura, le chiavi dell'infrastruttura a chiave pubblica (PKI) necessarie per le conferenze Skype for Business non possono essere salvate nel profilo. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisiti di sistema per Skype for Business per Windows Phone
 
 
Microsoft Skype for Business per Windows Phone fornisce messaggistica istantanea, presenza avanzata e telefonia per gli utenti dell'organizzazione che si connettono da uno smartphone o Windows Professional dispositivo mobile. I dispositivi mobili consentono agli utenti di estendere la portata Skype for Business. In questo argomento vengono descritte le considerazioni sulla pianificazione Skype for Business per Windows Phone che includono l'identificazione dei prerequisiti e dei requisiti tecnici, dei componenti necessari e delle linee guida per la distribuzione.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Skype for Business per Windows Phone prerequisiti

Di seguito sono riportati Skype for Business per Windows Phone prerequisiti.
  
- Windows Phone 8.1 o versione successiva.
    
- Il Windows Phone deve avere gli aggiornamenti più recenti disponibili da Microsoft. Per informazioni dettagliate, vedere la Windows Phone 8.1 in [Windows Phone 8 update history](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Il dispositivo deve avere 22 MB di spazio su disco disponibile.
    
- L'utente deve disporre di un piano voce e dati di un gestore telefonico.


## <a name="see-also"></a>Vedere anche

[Pianificare i client riunioni (App Web e app Riunioni)](meetings-clients.md)
  
[Skype for Business dei client Mac](mac-requirements.md)

[Scaricare Skype for Business tra tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 e Office di sistema](https://products.office.com/office-system-requirements)
