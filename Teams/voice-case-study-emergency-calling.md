---
title: 'Teams caso di studio contoso vocale: Chiamate di emergenza'
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
description: 'Teams case study vocale per multinazionali : Chiamate di emergenza'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69231adb4588039012cceec1063571ddc201c2bb
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587475"
---
# <a name="contoso-case-study-emergency-calling"></a>Caso di studio Contoso: Chiamate di emergenza

Per comprendere la disponibilità delle chiamate di emergenza e la terminologia relativa alle chiamate di emergenza, l'indirizzo, il luogo, la posizione per gli interventi di emergenza e l'indirizzo registrato Contoso ha esaminato Gestire le chiamate di emergenza e Pianificare e configurare le chiamate di emergenza &mdash; &mdash; [dinamiche.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)

In Office 365, un utente del Piano chiamate viene abilitato automaticamente per le chiamate di emergenza. Ma solo gli utenti del Piano chiamate negli Stati Uniti possono usare posizioni dinamiche per instradamento delle chiamate di emergenza. 

Per il routing diretto, Contoso ha appreso che è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza e, eventualmente, per la connettività dei partner. L'amministratore deve configurare la connessione a un provider di servizi di routing per gli interventi di emergenza (ERSP) (Stati Uniti) O configurare il Session Border Controller (SBC) per un'applicazione Emergency Location Identification Number (ELIN).

Contoso ha uffici negli Stati Uniti e all'esterno degli Stati Uniti:

- Negli Stati Uniti, gli utenti del piano chiamate Contoso possono usare posizioni dinamiche per instradamento delle chiamate di emergenza. 

- Al di fuori degli Stati Uniti, Contoso ha alcuni siti che usano piani per chiamate e alcuni siti connessi a Sistema telefonico tramite routing diretto.

## <a name="emergency-calling-use-cases"></a>Casi d'uso per chiamate di emergenza

Dopo aver deciso in che modo Contoso si connetterà Telefono sistema, Contoso ha identificato i casi d'uso per le chiamate di emergenza seguenti: 

- [Utente del piano di chiamata negli Stati Uniti](#calling-plan-user-in-the-united-states) 

- [Utente del piano di chiamata al di fuori degli Stati Uniti](#calling-plan-user-outside-of-the-united-states)

- [Utente che si connette a Sistema telefonico tramite routing diretto](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Utente del piano di chiamata negli Stati Uniti  

Ci sono requisiti per quando il numero di telefono deve essere associato a una posizione di emergenza. Per comprendere questi requisiti, Contoso ha esaminato [Considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

In base a questi requisiti, Contoso ha deciso di associare la località al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Utente del piano di chiamata al di fuori degli Stati Uniti 

Per capire quando un numero di telefono deve essere associato a una località di emergenza, Contoso ha esaminato [Considerazioni per i piani per le chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) In base ai requisiti, Contoso ha deciso quanto segue:  

-  Contoso associerà la località al numero di telefono quando un numero viene assegnato a un utente in Canada. 

- Contoso assegna una posizione di emergenza quando il numero di telefono viene acquistato da Office 365 o quando un numero viene trasferito da un altro provider di servizi o gestore. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Utente che si connette a Sistema telefonico tramite routing diretto 

Per pianificare il routing di emergenza per questo caso d'uso, Contoso ha esaminato [Considerazioni per il routing diretto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Poiché gli utenti di Routing diretto non ricevono chiamate di emergenza allo stesso modo degli utenti del piano di chiamata, Contoso ha dovuto decidere come fornire le chiamate di emergenza. Il routing diretto può essere connesso a un provider di servizi di routing di emergenza (ERSP). Il routing diretto può anche avere un SBC che include un codice ELIN (Emergency Location Identification Number).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considerazioni sul provider di servizi di routing di emergenza (ERSP)

I provider di servizi di routing di emergenza (ESP) possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.  

- Se un provider di servizi di routing per gli interventi di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente instradati al Punto di risposta per la sicurezza pubblica (PSAP) che serve tale posizione. 

- Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono prima schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base alla posizione aggiornata. 


#### <a name="elin-considerations"></a>Considerazioni sull'ELIN

Se un'applicazione SBC ELIN è integrata in una distribuzione di Routing diretto, è necessario eseguire altri passaggi di configurazione per associare gli indirizzi di emergenza ai numeri di telefono.  

Contoso ha deciso di usare i session border controller che includono applicazioni ELIN (Emergency Location Identification Number).  

## <a name="security-desk-notification"></a>Notifica di Security Desk

La possibilità di inviare una notifica al desk di sicurezza quando viene effettuato un intervento di emergenza è disponibile sia per i piani per chiamate Microsoft che per Sistema telefonico Direct Routing. Contoso ha esaminato i dettagli nella notifica di Security desk per determinare se deve essere configurato nei propri uffici  

Contoso ha deciso di usare la notifica del security desk.

## <a name="configuration"></a>Configurazione 

Contoso ha seguito la procedura descritta in [Configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) per: 

- Assegnare indirizzi di emergenza 

- Configurare le impostazioni di rete 

- Configurare il servizio informazioni sulla posizione 

- Configurare i criteri di emergenza 

- Abilitare utenti e siti 

- Testare le chiamate di emergenza 

Dopo aver configurato le chiamate di emergenza dinamiche, Contoso doveva assegnare la posizione all'utente appropriato.  

- Per aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere una posizione per gli interventi di [emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)

- Per creare luoghi per edifici, piani e uffici, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere un luogo per un [luogo per gli interventi di emergenza.](add-change-remove-emergency-place-organization.md) 

- Per assegnare una posizione per gli interventi di emergenza, Contoso ha seguito la procedura descritta in Assegnare o modificare una posizione per [gli interventi di emergenza per un utente.](assign-change-emergency-location-user.md) 

 
