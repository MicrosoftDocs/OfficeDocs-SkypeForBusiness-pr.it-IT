---
title: Case Study di teams Voice contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786029"
---
# <a name="contoso-case-study-emergency-calling"></a>Case Study di Contoso: chiamate di emergenza

Per comprendere la disponibilità di chiamate di emergenza e la terminologia relativa all'indirizzo di emergenza per le chiamate di emergenza &mdash; , luogo, luogo di emergenza e indirizzo registrato &mdash; Contoso Recensito [Gestisci chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) e [Pianifica e configura le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

In Office 365 un utente del piano di chiamata viene abilitato automaticamente per le chiamate di emergenza. Ma solo gli utenti del piano chiamante negli Stati Uniti possono usare posizioni dinamiche per il routing delle chiamate di emergenza. 

Per il routing diretto, Contoso ha imparato che è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza e possibilmente per la connettività dei partner. L'amministratore deve configurare la connessione a un provider di servizi di routing di emergenza (ERSP) (Stati Uniti) o configurare il session border controller (SBC) per un'applicazione ELIN (Emergency Location Identification Number).

Contoso ha uffici negli Stati Uniti ed esterni agli Stati Uniti:

- Negli Stati Uniti, contoso Calling Plan gli utenti possono usare posizioni dinamiche per il routing delle chiamate di emergenza. 

- Al di fuori degli Stati Uniti, Contoso ha alcuni siti che usano piani di chiamata e alcuni siti connessi al sistema telefonico tramite routing diretto.

## <a name="emergency-calling-use-cases"></a>Casi di utilizzo delle chiamate di emergenza

Dopo aver deciso in che modo Contoso si connette al sistema telefonico, Contoso ha identificato i casi di utilizzo delle chiamate di emergenza seguenti: 

- [Utente del piano chiamante negli Stati Uniti](#calling-plan-user-in-the-united-states) 

- [Utente del piano chiamante al di fuori degli Stati Uniti](#calling-plan-user-outside-of-the-united-states)

- [Utente che si connette al sistema telefonico tramite routing diretto](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Utente del piano chiamante negli Stati Uniti  

Esistono requisiti per i casi in cui il numero di telefono deve essere associato a una posizione di emergenza. Per comprendere questi requisiti, Contoso ha esaminato le [considerazioni per i piani di chiamata](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). 

In base a questi requisiti, Contoso ha deciso di associare la posizione al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Utente del piano chiamante al di fuori degli Stati Uniti 

Per capire quando un numero di telefono deve essere associato a una posizione di emergenza, Contoso ha esaminato le [considerazioni per i piani di chiamata](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans). In base ai requisiti, Contoso ha deciso quanto segue:  

-  Contoso associa la posizione al numero di telefono quando un numero viene assegnato a un utente in Canada. 

- Contoso assegnerà una posizione di emergenza quando il numero di telefono viene acquisito da Office 365 o quando un numero viene trasferito da un altro provider o gestore di servizi. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Utente che si connette al sistema telefonico tramite routing diretto 

Per pianificare il routing delle emergenze per questo caso di utilizzo, Contoso ha esaminato le [considerazioni per il routing diretto](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing). Poiché gli utenti del routing diretto non ricevono chiamate di emergenza allo stesso modo degli utenti del piano di chiamata, Contoso ha dovuto decidere come ottenere chiamate di emergenza. Il routing diretto può essere connesso a un provider di servizi di routing di emergenza (ERSP). Il routing diretto può anche avere un SBC che include un numero di identificazione della posizione di emergenza (ELIN).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considerazioni sul provider del servizio di routing (ERSP) Emergency

I provider di servizi di routing di emergenza (ERSPs) possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.  

- Se un provider di servizi di routing di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita in modo dinamico verranno indirizzate automaticamente al punto di PSAP (Public Safety Answering Point) che serve tale posizione. 

- Le chiamate di emergenza senza una posizione acquisita in modo dinamico vengono prima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base al percorso aggiornato. 


#### <a name="elin-considerations"></a>Considerazioni su ELIN

Se un'applicazione ELIN SBC è integrata in una distribuzione di routing diretto, è necessario che siano presenti ulteriori passaggi di configurazione per associare gli indirizzi di emergenza a numeri di telefono.  

Contoso ha deciso di usare i controller di bordo della sessione che includono le applicazioni ELIN (Emergency Location Identification Number).  

## <a name="security-desk-notification"></a>Notifica di Security desk

La possibilità di inviare una notifica al banco di sicurezza quando viene inserita una chiamata di emergenza è disponibile sia per i piani di chiamate Microsoft che per il routing diretto del sistema telefonico. Contoso ha esaminato i dettagli nella notifica di Security desk per determinare se la configurazione deve essere configurata presso gli uffici  

Contoso ha deciso di usare la notifica di Security desk.

## <a name="configuration"></a>Configurazione 

Contoso ha seguito la procedura descritta in [configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) in: 

- Assegnare indirizzi di emergenza 

- Configurare le impostazioni di rete 

- Configurare il servizio informazioni sulla posizione 

- Configurare i criteri di emergenza 

- Abilitare utenti e siti 

- Verificare le chiamate di emergenza 

Dopo la configurazione delle chiamate di emergenza dinamiche, contoso doveva assegnare la posizione all'utente appropriato.  

- Per aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione, Contoso ha seguito la procedura descritta in [aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)

- Per creare posizioni per edifici, pavimenti e uffici, Contoso ha seguito la procedura descritta in [aggiungere, modificare o rimuovere una posizione per un luogo di emergenza](add-change-remove-emergency-place-organization.md) . 

- Per assegnare una posizione di emergenza, Contoso ha seguito la procedura descritta in [assegnare o modificare una posizione di emergenza per un utente](assign-change-emergency-location-user.md). 

 