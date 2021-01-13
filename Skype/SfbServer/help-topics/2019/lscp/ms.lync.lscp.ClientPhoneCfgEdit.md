---
title: Configurazione del dispositivo creare nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina nuova configurazione dispositivo o modifica configurazione dispositivo è possibile creare o modificare una raccolta di impostazioni utilizzate per la gestione di Skype for Business Phone Edition. Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
ms.openlocfilehash: 0b330212c8dc050bb618f28ea6444b1c8e58f040
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830196"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configurazione dispositivo: crearne una nuova o modificarne una esistente
 
Nella pagina **nuova configurazione dispositivo** o **modifica configurazione dispositivo** è possibile creare o modificare una raccolta di impostazioni utilizzate per la gestione di Skype for Business Phone Edition. Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
  
## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:
  
- Aggiungere una nuova configurazione del dispositivo.
    
- Modificare le proprietà di una configurazione del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.
    
- **Nome** È possibile aggiungere o modificare il nome della configurazione del dispositivo.
    
- **Protezione SIP** È possibile configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Phone Edition. È possibile scegliere tra le opzioni seguenti:
    
  - **Bassa** Consenti qualsiasi tipo di autorizzazione o trasporto.
    
  - **Medie** NTLM o Kerberos è necessario per l'autenticazione dell'utente.
    
  - In **alto** Per l'autenticazione degli utenti è necessario NTLM o Kerberos e per le connessioni SIP è necessario TLS.
    
- **Livello di registrazione** È possibile abilitare la registrazione nel dispositivo UC. I valori validi sono Disattivato, Basso, Medio e Alto. Il valore predefinito è Disattivato.
    
- **Qualità del servizio (QoS) vocale** È possibile specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Phone Edition. Il valore predefinito è 40. Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46. Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.
    
- **Blocco del telefono** È possibile specificare se i telefoni UC si bloccano automaticamente dopo un determinato periodo di inattività. Di seguito sono descritte le impostazioni che possono essere configurate:
    
  - **Applicazione del blocco del dispositivo** È possibile applicare il blocco del dispositivo selezionando questa casella di controllo.
    
  - **Lunghezza minima PIN** È possibile specificare la lunghezza minima del PIN (Personal Identification Number) utilizzato per sbloccare il telefono. L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 numeri. La lunghezza predefinita è di sei numeri.
    
  - **Timeout di blocco del telefono** È possibile specificare il periodo di tempo minimo necessario per il blocco del telefono. L'intervallo per il timeout è compreso tra 0 e 60 minuti. il valore predefinito è 10 minuti. Immettere il valore nel formato HH: MM: SS.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
