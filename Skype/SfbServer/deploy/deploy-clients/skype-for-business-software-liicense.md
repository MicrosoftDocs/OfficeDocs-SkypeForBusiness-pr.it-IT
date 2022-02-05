---
title: Skype room system Skype for Business licenza software
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
  - NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza Skype for Business software.
---

# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business licenza software
 
Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza Skype for Business software. 
  
Skype Room System usa un client Skype for Business, che richiede un contratto multilicenza software. Prima di distribuire il primo Skype Room System, individuare lo stato dei contratti multilicenza della distribuzione, utilizzando i server di gestione delle chiavi (Servizio di gestione delle chiavi) o più chiavi di attivazione (MAK).
  
## <a name="key-management-servers-kms"></a>Server di gestione delle chiavi (Servizio di gestione delle chiavi)

Se Servizio di gestione delle chiavi sono presenti e distribuiscono Skype for Business di contratti multilicenza, il Skype Room System attiverà automaticamente il client Skype for Business locale. Per scoprire se Servizio di gestione delle chiavi sono in atto:
  
Da un prompt dei comandi eseguire:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Per configurare un Servizio di gestione delle chiavi, vedere Servizio di gestione delle chiavi [activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e [GVLKs for Servizio di gestione delle chiavi and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Questa chiave fa in modo che Skype Room System cerca un Servizio di gestione delle chiavi nella rete).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Codici ad attivazione multipla (MAK) dal Centro servizi per contratti multilicenza (VLSC)

Se il cliente usa qualsiasi altro software con contratti multilicenza, il reparto IT gestirà le attivazioni software e il Contratto multilicenza (VLA) tramite VLSC. In questo modo la società potrà anche acquistare Skype for Business attivazioni VL, dopo di che la società potrà ottenere un codice ADK per l'input nella console di amministrazione di Skype Room System.
  
Un cliente con una VLA deve conoscere le proprie credenziali VLSC, che verranno utilizzate per amministrare il contratto e ottenere il codice ADK. In caso di dubbi, il reparto finanziario del cliente dovrebbe essere in grado di verificare se il cliente ha pagato una VLA.
  
Per ottenere un codice ADK, accedere al Centro servizi per contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK). Per altre informazioni, vai al [Centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>Codice ad attivazione Microsoft 365 o Office 365 senza accesso VLSC

Se il cliente non ha un Contratto multilicenza, Skype for Business le attivazioni saranno molto più difficili da gestire. Tuttavia, Microsoft 365 e Office 365 senza accesso VLSC possono ottenere un codice ADK promozionale fornendo le seguenti informazioni all'OEM che vende il Skype Room System:
  
- Nome dell'azienda
    
- Nome del contatto di distribuzione, indirizzo di posta elettronica e numero di telefono
    
- Numero di sistemi distribuiti
    
- Data distribuzione
    
- Se il cliente dispone di un Microsoft Technical Account Manager, il nome e le informazioni di contatto del TAM
