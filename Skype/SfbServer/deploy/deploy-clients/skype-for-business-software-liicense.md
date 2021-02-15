---
title: Licenza software Skype for Business per Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833926"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: licenza software Skype for Business
 
Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business. 
  
Skype Room System usa un client Skype for Business installato, che richiede un contratto multilicenza software. Prima di distribuire il primo Skype Room System, scopri lo stato dei contratti multilicenza della distribuzione usando i server di gestione delle chiavi (KMS) o più codici ad attivazione multipla (MAK).
  
## <a name="key-management-servers-kms"></a>Server di gestione delle chiavi (KMS)

Se il servizio di gestione delle chiavi è sul posto e distribuirà le attivazioni dei contratti multilicenza di Skype for Business, Skype Room System attiverà automaticamente il client Skype for Business. Per scoprire se il servizio di gestione delle chiavi è sul posto:
  
Da un prompt dei comandi eseguire:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Per ulteriori informazioni, vedere Come individuare gli host del Servizio di gestione delle chiavi di Office e [Windows tramite DNS e rimuovere istanze non autorizzate.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Per configurare un servizio di gestione delle chiavi, vedere [KmS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Codice Product Key per contratti multilicenza generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questo codice fa sì che Skype Room System cerca un servizio di gestione delle chiavi nella rete).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Codici "Product Key" per attivazione multipla (MAK) dal Centro servizi per contratti multilicenza

Se il cliente usa qualsiasi altro software con contratto multilicenza, il reparto IT gestirà le attivazioni software e il Contratto multilicenza (VLA) tramite VLSC. Ciò consentirà anche all'azienda di acquistare le attivazioni VL di Skype for Business, dopo di che l'azienda può ottenere un codice ad attivazione multipla per l'input nella console di amministrazione di Skype Room System.
  
Un cliente con una VLA deve conoscere le proprie credenziali VLSC, che verranno usate per amministrare il contratto e ottenere il codice ad attivazione attivazione attivazione software. In caso di dubbi, il reparto finanze del cliente dovrebbe essere in grado di confermare se il cliente ha pagato una VLA.
  
Per ottenere un codice "Product Key" per attivazione programmi, accedere al Centro servizi per contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK). Per ulteriori informazioni, visitare il Centro servizi [per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>Codice ad attivazione attivazione attivazione programmi per Microsoft 365 o Office 365 senza accesso VLSC

Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for Business saranno molto più difficili da gestire. Tuttavia, i clienti di Microsoft 365 e Office 365 senza accesso VLSC possono ottenere un codice "MaK" promozionale fornendo le informazioni seguenti all'OEM che vende Skype Room System:
  
- Nome dell'azienda
    
- Nome del contatto di distribuzione, indirizzo di posta elettronica e numero di telefono
    
- Numero di sistemi distribuiti
    
- Data distribuzione
    
- Se il cliente ha un responsabile dell'account tecnico Microsoft, il nome e le informazioni di contatto del TAM
    

