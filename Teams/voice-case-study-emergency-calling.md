---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786029"
---
# <a name="contoso-case-study-emergency-calling"></a>Case study Contoso: Chiamate di emergenza

Per conoscere la disponibilità delle chiamate di emergenza e la terminologia relativa all'indirizzo di emergenza, al luogo, alla posizione per gli interventi di emergenza e all'indirizzo registrato Contoso ha esaminato Gestisci chiamate di emergenza e Pianifica e configura le chiamate di emergenza &mdash; &mdash; dinamiche. [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)

In Office 365, un utente del Piano per chiamate viene abilitato automaticamente per le chiamate di emergenza. Tuttavia, solo gli utenti del Piano per chiamate negli Stati Uniti possono utilizzare posizioni dinamiche per l'instradamento delle chiamate di emergenza. 

Per l'instradamento diretto, Contoso ha appreso che è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e probabilmente per la connettività del partner. L'amministratore deve configurare la connessione a un provider del servizio di instradamento di emergenza (ERSP) (Stati Uniti) O configurare il controller dei confini della sessione (SBC) per un'applicazione ELIN (Emergency Location Identification Number).

Contoso ha uffici negli Stati Uniti e al di fuori degli Stati Uniti:

- Negli Stati Uniti, gli utenti del Piano per chiamate Contoso possono utilizzare posizioni dinamiche per l'instradamento delle chiamate di emergenza. 

- Al di fuori degli Stati Uniti, Contoso ha alcuni siti che utilizzano Piani per chiamate e altri sono connessi al Sistema telefonico attraverso l'instradamento diretto.

## <a name="emergency-calling-use-cases"></a>Casi d'uso per le chiamate di emergenza

Dopo aver deciso come Contoso si connetterà al sistema telefonico, Contoso ha identificato i seguenti casi d'uso per le chiamate di emergenza: 

- [Utente del Piano per chiamate negli Stati Uniti](#calling-plan-user-in-the-united-states) 

- [Utente del Piano per chiamate al di fuori degli Stati Uniti](#calling-plan-user-outside-of-the-united-states)

- [Utente che si connette al Sistema telefonico tramite routing diretto](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>Utente del Piano per chiamate negli Stati Uniti  

Ci sono dei requisiti quando il numero di telefono deve essere associato a una posizione per gli interventi di emergenza. Per comprendere questi requisiti, Contoso ha esaminato [considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

In base a questi requisiti, Contoso ha deciso di associare la località al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.

### <a name="calling-plan-user-outside-of-the-united-states"></a>Utente del Piano per chiamate al di fuori degli Stati Uniti 

Per capire quando un numero di telefono deve essere associato a una posizione per gli interventi di emergenza, Contoso ha esaminato [considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) In base ai requisiti, Contoso ha deciso quanto segue:  

-  Contoso associa la località al numero di telefono quando viene assegnato un numero a un utente in Canada. 

- Contoso assegna una posizione per gli interventi di emergenza quando il numero di telefono viene acquisito da Office 365 o quando un numero viene trasferito da un altro fornitore di servizi o gestore. 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>Utente che si connette al Sistema telefonico tramite routing diretto 

Per pianificare l'instradamento di emergenza per questo caso di utilizzo, Contoso ha esaminato [considerazioni per il routing diretto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing) Poiché gli utenti con instradamento diretto non ricevono le chiamate di emergenza come gli utenti del Piano per chiamate, Contoso ha dovuto decidere come effettuare le chiamate di emergenza. L'instradamento diretto può essere connesso a un provider di servizi di instradamento di emergenza (ERSP, Emergency Routing Service). L'instradamento diretto può anche avere un SBC che include un numero ELIN (Emergency Location Identification Number).   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>Considerazioni sul provider di servizi di emergenza (EERSP, Emergency Routing Service Provider)

Gli operatori del servizio di instradamento di emergenza possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.  

- Se un provider di servizi di instradamento di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente indirizzate al punto PSAP (Public Safety Answering Point) che serve tale posizione. 

- Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono innanzitutto schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di emergenza appropriato in base alla posizione aggiornata. 


#### <a name="elin-considerations"></a>Considerazioni sull'ELIN

Se un'applicazione SBC ELIN è integrata in una distribuzione di routing diretto, è necessario eseguire altri passaggi di configurazione per associare gli indirizzi di emergenza ai numeri di telefono.  

Contoso ha deciso di usare i controller dei confini della sessione che includono applicazioni ELIN (Emergency Location Identification Number).  

## <a name="security-desk-notification"></a>Notifica security desk

La possibilità di avvisare il desk sicurezza durante l'esecuzione di una chiamata di emergenza è disponibile sia per i Piani per chiamate Microsoft che per l'instradamento diretto del sistema telefonico. Contoso ha esaminato i dettagli nella notifica security desk per determinare se deve essere configurato negli uffici  

Contoso ha deciso di usare la notifica del security desk.

## <a name="configuration"></a>Configurazione 

Contoso ha seguito la procedura descritta in [Configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) per: 

- Assegnare indirizzi per gli interventi di emergenza 

- Configurare le impostazioni di rete 

- Configurazione del servizio informazioni sulla posizione 

- Configurare i criteri di emergenza 

- Abilitare utenti e siti 

- Testare le chiamate d'emergenza 

Dopo aver configurato le chiamate di emergenza dinamiche, Contoso deve assegnare la posizione all'utente appropriato.  

- Per aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione, Contoso ha seguito la procedura aggiunta, modifica o rimozione di una posizione per gli interventi di [emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)

- Per creare luoghi per edifici, piani e uffici, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere un luogo per una posizione per [gli interventi di emergenza.](add-change-remove-emergency-place-organization.md) 

- Per assegnare una posizione per gli interventi di emergenza, Contoso ha seguito la procedura descritta in Assegnare o modificare una posizione per [gli interventi di emergenza per un utente.](assign-change-emergency-location-user.md) 

 