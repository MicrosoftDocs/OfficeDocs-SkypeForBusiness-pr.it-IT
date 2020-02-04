---
title: Configurazione del dispositivo crea nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Nella pagina Configurazione nuovo dispositivo o modifica dispositivo è possibile creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Phone Edition. Queste impostazioni consentono di configurare aspetti come la modalità di sicurezza richiesta, il livello di registrazione dei dispositivi, le impostazioni di Qualità del servizio (QoS) e il blocco automatico dei telefoni dopo un periodo di inattività specificato.
ms.openlocfilehash: 0bd8d79a97f9dd48faff09f1d7a8e0cfb41473f6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700321"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configurazione dispositivo: crearne una nuova o modificarne una esistente
 
Nella pagina configurazione **nuovo dispositivo** o **modifica dispositivo** è possibile creare o modificare una raccolta di impostazioni usate per gestire Skype for Business Phone Edition. Queste impostazioni consentono di configurare aspetti come la modalità di sicurezza richiesta, il livello di registrazione dei dispositivi, le impostazioni di Qualità del servizio (QoS) e il blocco automatico dei telefoni dopo un periodo di inattività specificato.
  
## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Nuova configurazione dispositivo** o **Modifica configurazione dispositivo** è possibile eseguire le attività seguenti:
  
- Aggiungere una nuova configurazione del dispositivo.
    
- Modificare le proprietà di una configurazione del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del dispositivo.
    
- **Nome** È possibile aggiungere o modificare il nome della configurazione del dispositivo.
    
- **Sicurezza SIP** È possibile configurare i requisiti di trasporto e autenticazione per i dispositivi Skype for Business Phone Edition. È possibile scegliere tra le opzioni seguenti:
    
  - **Basso** Consentire qualsiasi tipo di autorizzazione o trasporto.
    
  - **Medio** È necessario NTLM o Kerberos per l'autenticazione utente.
    
  - **Alto** È necessario NTLM o Kerberos per l'autenticazione dell'utente e TLS è necessario per le connessioni SIP.
    
- **Livello di registrazione** È possibile abilitare la registrazione nel dispositivo UC. I valori validi sono Disattivato, Basso, Medio e Alto. Il valore predefinito è Disattivato.
    
- **Qualità del servizio (QoS) vocale** Puoi specificare il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Skype for Business Phone Edition. Il valore predefinito è 40. Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46. Per mantenere la coerenza nella rete, è consigliabile modificare questo valore in 46.
    
- **Blocco telefono** È possibile specificare se i telefoni UC si bloccano automaticamente dopo un periodo di inattività specificato. Di seguito sono descritte le impostazioni che possono essere configurate:
    
  - **Applicare il blocco del dispositivo** È possibile applicare il blocco del dispositivo selezionando questa casella di controllo.
    
  - **Lunghezza minima del pin** È possibile specificare la lunghezza minima per il PIN (Personal Identification Number) usato per sbloccare il telefono. L'intervallo di valori per la lunghezza del PIN è compreso tra quattro e 15 cifre. La lunghezza predefinita è di sei cifre.
    
  - **Timeout blocco telefono** È possibile specificare il periodo di tempo minimo prima che il telefono si blocchi. L'intervallo per il timeout è compreso tra 0 e 60 minuti; il valore predefinito è di 10 minuti. Immettere il valore nel formato HH: MM: SS.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dispositivo](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
