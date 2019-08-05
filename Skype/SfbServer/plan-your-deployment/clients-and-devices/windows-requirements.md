---
title: Requisiti del client Windows e supporto software
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 'Riepilogo: rivedere i requisiti di supporto di Windows client durante la pianificazione di Skype for Business Server.'
ms.openlocfilehash: bbcbf11da53b2895f04725fda57342c17989b7f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187865"
---
# <a name="windows-client-requirements-and-software-support"></a>Requisiti del client Windows e supporto software
 
**Riepilogo:** Esaminare i requisiti di supporto client Windows durante la pianificazione di Skype for Business Server.
  
Questa sezione riepiloga il software necessario per supportare i client Windows Skype for business.  Questi client vengono installati quando si installa Office 365 e sono disponibili anche [per scaricare Skype for business in tutti i dispositivi](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3).
  
> [!NOTE]
> Il componente aggiuntivo riunione online per Skype for business, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Skype for business. 
  
**Software necessario per il client Skype for business e il componente aggiuntivo riunione online**

|**Componente di sistema**|**Versioni supportate**|
|:-----|:-----|
|Sistema operativo Windows  <br/> |Windows 10  <br/> Windows 8,1  <br/> Windows 8  <br/> Sistema operativo Windows 7  <br/> Windows Server 2008 R2 o versioni successive con il Service Pack più recente  <br/> **Nota:** Skype for business e il componente aggiuntivo per le riunioni online per Skype for business non sono supportati in Windows Vista o Windows XP (qualsiasi versione). <br/> |
|Installazione e aggiornamenti  <br/> |Diritti di amministratore e autorizzazioni  <br/> |
|Browser  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet browser  <br/>  Web browser Internet Explorer 10 <br/> Internet Explorer 9 Internet browser  <br/> Web browser Internet Explorer 8  <br/> Browser Internet di Internet Explorer 7  <br/> Web browser Mozilla Firefox  <br/>  Web browser di Google Chrome  <br/>**Nota:** Se si usa Skype for business con Microsoft Exchange Online e l'organizzazione ha distribuito un proxy HTTP di autenticazione, è necessario Internet Explorer 8 o versione successiva.           |
|Integrazione di Microsoft Office  <br/> | Outlook 2010 o versione successiva |
|Integrazione con Microsoft Exchange  <br/> | Microsoft Exchange Server 2010 o versione successiva  | 
   
## <a name="hardware"></a>Hardware

Fare riferimento ai requisiti di [sistema](https://products.office.com/en-us/office-system-requirements) di Office 365 per l'hardware necessario per eseguire il client Skype for business.
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>App riunioni Skype e Skype for Business Web App 

L'app riunioni Skype e Skype for business web app supportano combinazioni specifiche di sistemi operativi e browser. Per informazioni dettagliate, vedere [pianificare i client di riunioni (app Web e riunioni)](meetings-clients.md). 
  
## <a name="using-mandatory-profiles"></a>Uso dei profili obbligatori

Se si prevede di usare le funzionalità di conferenza di Skype for business, evitare di usare i profili obbligatori dei servizi di dominio Active Directory per accedere al client Skype for business. Poiché i profili obbligatori sono profili utente di sola lettura, le chiavi dell'infrastruttura a chiave pubblica (PKI) necessarie per i servizi di conferenza Skype for business non possono essere salvate nel profilo. 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Requisiti di sistema per Skype for business per Windows Phone
 
 
Microsoft Skype for business per Windows Phone offre messaggistica istantanea, presenza avanzata e telefonia per gli utenti dell'organizzazione che si connettono da uno smartphone o da un dispositivo mobile Windows Professional. I dispositivi mobili consentono agli utenti di estendere la portata di Skype for business. Questo argomento descrive le considerazioni sulla pianificazione per Skype for business per Windows Phone che includono l'individuazione di prerequisiti e requisiti tecnici, componenti necessari e indicazioni per la distribuzione.
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Prerequisiti di Skype for business per Windows Phone

Di seguito sono riportati i prerequisiti di Skype for business per Windows Phone.
  
- Windows Phone 8,1 o versione successiva.
    
- Il dispositivo Windows Phone deve avere gli aggiornamenti più recenti disponibili in Microsoft. Per informazioni dettagliate, vedere la sezione Windows Phone 8,1 nella [cronologia degli aggiornamenti di Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961).
    
- Il dispositivo deve avere 22 MB di spazio disponibile su disco.
    
- L'utente deve avere un piano per la voce e i dati da un gestore.


## <a name="see-also"></a>Vedere anche

[Pianificare i client delle riunioni (app Web e riunioni)](meetings-clients.md)
  
[Requisiti client Skype for business per Mac](mac-requirements.md)

[Scaricare Skype for business in tutti i dispositivi](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Requisiti di sistema di Office 365](https://products.office.com/en-us/office-system-requirements)
