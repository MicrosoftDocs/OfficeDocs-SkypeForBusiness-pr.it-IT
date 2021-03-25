---
title: Skype Room System Licenza software Skype for Business
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
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113092"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: licenza software Skype for Business
 
Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business. 
  
Skype Room System usa un client Skype for Business installato, che richiede un contratto multilicenza software. Prima di distribuire il primo skype room system, scopri lo stato dei contratti multilicenza della distribuzione, usando i server di gestione delle chiavi (KMS) o più chiavi di attivazione (MAK).
  
## <a name="key-management-servers-kms"></a>Server di gestione delle chiavi (KMS)

Se il servizio di gestione delle chiavi è sul posto e distribuisce le attivazioni dei contratti multilicenza Skype for Business, skype room system attiverà automaticamente il client Skype for Business. Per scoprire se il servizio di gestione delle chiavi è in atto:
  
Da un prompt dei comandi eseguire:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Per ulteriori informazioni, vedere Come individuare gli host del servizio di gestione delle chiavi di Office e [Windows tramite DNS e rimuovere istanze non autorizzate.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Per configurare un servizio di gestione delle chiavi, vedere Attivazione del servizio di gestione delle chiavi di [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e GVK per il servizio di gestione delle chiavi e l'attivazione di Active Directory di [Office 2013](/DeployOffice/vlactivation/gvlks)
  
Codice Product Key per contratti multilicenza generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Questa chiave fa sì che Skype Room System cerca un servizio di gestione delle chiavi nella rete).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Codici ad attivazione multipla (MAK) dal Centro servizi per contratti multilicenza (VLSC)

Se il cliente usa qualsiasi altro software con contratti multilicenza, il reparto IT gestirà le attivazioni software e il Contratto multilicenza (VLA) tramite VLSC. In questo modo la società potrà anche acquistare le attivazioni VL di Skype for Business, dopo di che l'azienda potrà ottenere un codice ADK per l'input nella Console di amministrazione di Skype Room System.
  
Un cliente con una VLA deve conoscere le proprie credenziali VLSC, che verranno utilizzate per amministrare il contratto e ottenere il codice ADK. In caso di dubbi, il reparto finanziario del cliente dovrebbe essere in grado di verificare se il cliente ha pagato una VLA.
  
Per ottenere un codice ADK, accedere al Centro servizi per contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK). Per ulteriori informazioni, passare al [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>Codice AdO per Microsoft 365 o Office 365 senza accesso VLSC

Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for Business saranno molto più difficili da gestire. Tuttavia, i clienti di Microsoft 365 e Office 365 senza accesso VLSC possono ottenere un codice ADK promozionale fornendo le informazioni seguenti all'OEM che vende skype room system:
  
- Nome dell'azienda
    
- Nome del contatto di distribuzione, indirizzo di posta elettronica e numero di telefono
    
- Numero di sistemi distribuiti
    
- Data distribuzione
    
- Se il cliente ha un Microsoft Technical Account Manager, il nome e le informazioni di contatto del TAM
