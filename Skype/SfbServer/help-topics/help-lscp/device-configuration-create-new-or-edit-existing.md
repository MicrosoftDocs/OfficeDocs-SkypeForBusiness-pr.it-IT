---
title: Configurazione dispositivo Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Nella pagina Nuova configurazione dispositivo o Modifica configurazione dispositivo è possibile creare o modificare una raccolta di impostazioni utilizzate per gestire Skype for Business Phone Edition. Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807306"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configurazione dispositivo: crearne una nuova o modificarne una esistente
 
Nella pagina **Nuova configurazione dispositivo** o Modifica configurazione dispositivo è possibile creare o modificare una raccolta di impostazioni utilizzate per gestire Skype for Business Phone Edition.  Tali impostazioni consentono di configurare aspetti quali la modalità di sicurezza richiesta, il livello di registrazione del dispositivo, le impostazioni Qualità vocale servizio (QoS) e se bloccare automaticamente o meno i telefoni dopo uno specifico periodo di inattività.
  
## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:
  
- Aggiungere una nuova configurazione del dispositivo.
    
- Modificare le proprietà di una configurazione del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.
    
- **Name** Puoi aggiungere o modificare il nome della configurazione del dispositivo.
    
- **Sicurezza SIP** È possibile configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Phone Edition. È possibile scegliere tra le opzioni seguenti:
    
  - **Basso** Consentire qualsiasi tipo di autorizzazione o trasporto.
    
  - **Medio** Per l'autenticazione degli utenti è necessario NTLM o Kerberos.
    
  - **High** NtLM o Kerberos è necessario per l'autenticazione utente e TLS è necessario per le connessioni SIP.
    
- **Livello di registrazione** È possibile abilitare la registrazione nel dispositivo per le comunicazioni unificate. I valori validi sono Disattivato, Basso, Medio e Alto. Il valore predefinito è Disattivato.
    
- **Qualità del servizio vocale (QoS)** È possibile specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Phone Edition. Il valore predefinito è 40. Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46. Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.
    
- **Blocco telefono** È possibile specificare se i telefoni per le comunicazioni unificate si bloccano automaticamente dopo un periodo di inattività specificato. Di seguito sono descritte le impostazioni che possono essere configurate:
    
  - **Applicare il blocco dei dispositivi** È possibile applicare il blocco del dispositivo selezionando questa casella di controllo.
    
  - **Lunghezza minima PIN** È possibile specificare la lunghezza minima per il PIN utilizzato per sbloccare il telefono. L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 numeri. La lunghezza predefinita è di sei numeri.
    
  - **Timeout blocco telefono** È possibile specificare il periodo di tempo minimo prima che il telefono si blocchi. L'intervallo per il timeout è compreso tra 0 e 60 minuti. il valore predefinito è 10 minuti. Immettere il valore nel formato HH:MM:SS.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dispositivo](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
