---
title: Configurazione dispositivo Crea nuovo o Modifica esistente
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
description: Nella pagina Nuova configurazione dispositivo o Modifica configurazione dispositivo puoi creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Telefono Edition. Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
ms.openlocfilehash: f19a3d6018252fd0abc1ca717b50230aa5f063516e018e2b5b1745fa06a60388
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316332"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configurazione dispositivo: crearne una nuova o modificarne una esistente
 
Nella pagina **Nuova configurazione dispositivo** o Modifica configurazione dispositivo puoi creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Telefono Edition.  Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
  
## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:
  
- Aggiungere una nuova configurazione del dispositivo.
    
- Modificare le proprietà di una configurazione del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.
    
- **Nome** Puoi aggiungere o modificare il nome della configurazione del dispositivo.
    
- **Sicurezza SIP** Puoi configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Telefono Edition. È possibile scegliere tra le opzioni seguenti:
    
  - **Bassa** Consentire qualsiasi tipo di autorizzazione o trasporto.
    
  - **Medio** Per l'autenticazione utente è necessario NTLM o Kerberos.
    
  - **High** NtLM o Kerberos è necessario per l'autenticazione utente e TLS è necessario per le connessioni SIP.
    
- **Livello di registrazione** È possibile abilitare la registrazione nel dispositivo per le comunicazioni unificate. I valori validi sono Disattivato, Basso, Medio e Alto. Il valore predefinito è Disattivato.
    
- **Qualità del servizio vocale (QoS)** Puoi specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Telefono Edition. Il valore predefinito è 40. Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46. Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.
    
- **Telefono blocco** È possibile specificare se i telefoni UC verranno automaticamente bloccati dopo un periodo di inattività specificato. Di seguito sono descritte le impostazioni che possono essere configurate:
    
  - **Applicare il blocco dei dispositivi** Puoi applicare il blocco dei dispositivi selezionando questa casella di controllo.
    
  - **Lunghezza minima PIN** È possibile specificare la lunghezza minima per il PIN (Personal Identification Number) utilizzato per sbloccare il telefono. L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 numeri. La lunghezza predefinita è di sei numeri.
    
  - **Telefono timeout del blocco** Puoi specificare il periodo di tempo minimo prima che il telefono si blocchi. L'intervallo per il timeout è compreso tra 0 e 60 minuti. il valore predefinito è 10 minuti. Immettere il valore nel formato HH:MM:SS.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)