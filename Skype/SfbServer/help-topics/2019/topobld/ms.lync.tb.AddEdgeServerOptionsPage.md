---
title: Aggiungere opzioni per il server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: "Selezionare tutte le funzionalità che si desidera abilitare per il pool Edge Server. Per impostazione predefinita, il pool di server perimetrali supporta gli utenti remoti dell'organizzazione che a cui a loro accede dall'esterno del firewall utilizzando una rete privata virtuale (VPN). Sono disponibili le opzioni seguenti per le funzionalità del pool Edge Server:"
ms.openlocfilehash: 943a2a7b96fa8bcfd00e3c21631f763ad056b31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800936"
---
# <a name="add-edge-server-options"></a>Aggiungere opzioni Edge Server

Selezionare tutte le funzionalità che si desidera abilitare per il pool Edge Server. Per impostazione predefinita, il pool di server perimetrali supporta gli utenti remoti dell'organizzazione che a cui a loro accede dall'esterno del firewall utilizzando una rete privata virtuale (VPN). Sono disponibili le opzioni seguenti per le funzionalità del pool Edge Server:

- Utilizzo di un solo nome di dominio completo (FQDN) e di un solo indirizzo IP per tutti i servizi Edge, ovvero il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge. Se non si seleziona l'opzione per l'utilizzo di un solo FQDN e di un solo indirizzo IP, sarà necessario specificare un FQDN e un indirizzo IP distinti per ognuno di questi tre servizi Edge durante il processo di distribuzione. Per informazioni dettagliate sui servizi Edge, vedere [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) nella documentazione relativa alla pianificazione.

    > [!NOTE]
    > Se si seleziona questa opzione, sarà necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni delle porte predefinite consigliate: 444 per il servizio Access Edge, 8057 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando tale opzione, è possibile evitare più facilmente problemi di connettività e semplificare la configurazione perché è poi necessario immettere un solo FQDN che viene utilizzato per tutti e tre i servizi.

- Supporto della federazione. Selezionare questa opzione se si desidera supportare la comunicazione tra gli utenti interni e gli utenti di domini trusted all'esterno dell'organizzazione, inclusi gli eventuali utenti di un provider di servizi di messaggistica istantanea pubblici supportato. Se si seleziona questa opzione, sarà necessario configurare il supporto per i domini federati e i provider di servizi di connettività di messaggistica istantanea pubblici specifici che si desidera supportare. Per informazioni dettagliate sulla configurazione del supporto per la federazione e altri tipi di accesso utente esterno, vedere [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) nella documentazione relativa alla distribuzione di server perimetrali.

    > [!NOTE]
    > Solo un pool Front End o un server perimetrale Standard dell'organizzazione può essere pubblicato esternamente per la federazione. Qualsiasi accesso da parte di utenti federati, inclusi gli utenti di servizi di messaggistica istantanea pubblici, passa attraverso lo stesso pool di server perimetrali o lo stesso server perimetrale singolo. Se ad esempio nella distribuzione è incluso un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto della federazione per il pool di server perimetrali o il singolo server perimetrale di New York, il traffico di segnalazione per gli utenti federati passerà attraverso tale pool o server. Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.

- Abilita federazione XMPP. Selezionare questa opzione se si desidera supportare la comunicazione tra utenti interni e partner XMPP attendibili.

È possibile aggiungere il supporto dell'accesso utente esterno quando si distribuisce la topologia iniziale o successivamente. Per informazioni dettagliate sull'aggiunta di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.


