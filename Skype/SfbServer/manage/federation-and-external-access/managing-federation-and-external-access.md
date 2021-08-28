---
title: "Lync Server 2013: Gestione della federazione e dell'accesso esterno Skype for Business Server"
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: È possibile abilitare e configurare l'accesso degli utenti esterni per controllare se gli utenti esterni supportati possono collaborare con utenti Skype for Business Server interni.
ms.openlocfilehash: aab0a4c5a3613f285b47a886819d524e37480341
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590140"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestione della federazione e dell'accesso esterno Skype for Business Server

La distribuzione di un server perimetrale o di un pool di server perimetrali è il primo passaggio per il supporto degli utenti esterni. Per informazioni dettagliate sulla distribuzione dei server perimetrali, vedere [Deploy Edge Server in Skype for Business Server.](../../deploy/deploy-edge-server/deploy-edge-server.md)

Dopo aver installato e configurato la distribuzione interna di Skype for Business Server, gli utenti interni dell'organizzazione possono collaborare con altri utenti interni che dispongono di account SIP in Servizi di dominio Active Directory. La collaborazione può includere l'invio e la ricezione di messaggi istantanei, l'aggiornamento delle informazioni sulla presenza e la partecipazione a conferenze, anche note come "riunioni". È possibile abilitare e configurare l'accesso degli utenti esterni per controllare se gli utenti esterni supportati possono collaborare con utenti Skype for Business Server interni. Gli utenti esterni possono includere utenti remoti della distribuzione, utenti federati (inclusi gli utenti supportati di provider di servizi di messaggistica istantanea pubblici) e partecipanti anonimi alle conferenze.

Se la distribuzione includeva l'installazione di un server perimetrale di Skype for Business Server o di un pool di server perimetrali, l'ambito dei possibili tipi di comunicazione è notevolmente ampliato con una serie di opzioni per l'accesso degli utenti esterni, la comunicazione con i membri di altri domini federati SIP e provider federati SIP. Dopo aver configurato il server perimetrale o il pool di server perimetrali, è possibile abilitare i tipi di accesso utente esterno che si desidera fornire e configurare i criteri da controllare per l'accesso esterno. In Skype for Business Server, si abilitano e configurano l'accesso utente esterno e i criteri utilizzando il Pannello di controllo di Skype for Business Server, [Skype for Business Server Management Shell](../management-shell.md)o entrambi, in base ai requisiti dell'attività. 



> [!IMPORTANT]  
> Quando si progettano la configurazione e i criteri per l'accesso utente esterno, è necessario conoscere la precedenza dei criteri e la modalità di applicazione degli stessi. Skype for Business Server impostazioni dei criteri applicate a un livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.


Per impostazione predefinita, non vengono configurati criteri per supportare l'accesso utente esterno, incluso l'accesso di utenti remoti e di utenti federati, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'utilizzo dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Sono inclusi i criteri di accesso esterno seguenti:

  - **Criterio globale**   Il criterio globale viene creato quando si distribuiscono i server perimetrali. Per impostazione predefinita, nel criterio globale non sono abilitate opzioni di accesso degli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, configurare il criterio globale per il supporto di uno o più tipi di opzioni di accesso di utenti esterni. Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri sito e utente hanno la priorità sul criterio globale. Se si elimina il criterio globale, il criterio non viene rimosso, ma vengono ripristinate le impostazioni predefinite.

  - **Criterio sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.

  - **Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso utente remoto a utenti specifici. La configurazione dei criteri utente ha la precedenza sui criteri globali e sui criteri sito, ma solo per gli utenti specifici a cui sono assegnati i criteri utente. Se, ad esempio, si abilita l'accesso utente remoto nei criteri globali e nei criteri sito, è possibile specificare criteri utente tramite cui viene disabilitato l'accesso utente remoto e quindi assegnare tali criteri a utenti specifici. Se si creano criteri utente, è necessario applicarli a uno o più utenti affinché diventino attivi.


Per stabilire quali impostazioni di configurazione e quali criteri è necessario creare o modificare, considerare gli aspetti seguenti:

**Si desidera offrire agli utenti interni ed esterni del dominio la possibilità di collaborare tramite le funzionalità di messaggistica istantanea, Web Conferencing e audio/video?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to control remote user acces](external-access-policies/configure-policies-to-control-remote-user-access.md)e Enable or disable federation and public IM [connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Si desidera consentire agli utenti anonimi di partecipare ed essere invitati a conferenze ospitate da utenti inclusi nella distribuzione?**

Configurare le impostazioni come descritto nell'argomento Assegnare criteri di conferenza [per supportare](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) gli utenti anonimi [e Creare criteri conferenza.](../conferencing/create-policies.md)

**Si desidera consentire agli utenti di comunicare con i contatti dei domini federati SIP?**

Configurare le impostazioni come descritto negli argomenti Configure [policies to control federated user access,](external-access-policies/configure-policies-to-control-federated-user-access.md) [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e Manage [SIP federated domains for your organization](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Se è stata abilitata la comunicazione con i domini federati SIP, si desidera abilitare l'individuazione automatica della federazione SIP?**

Configurare le impostazioni come descritto nell'argomento [Abilitare o disabilitare l'individuazione dei partner federativi.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Se le comunicazioni con i domini federati SIP sono state abilitate, si desidera abilitare l'invio di una dichiarazione di non responsabilità ai contatti federati per avvisarli che è in uso l'archiviazione e che le comunicazioni potrebbero essere archiviate?**

Configurare le impostazioni come descritto nell'argomento Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità di archiviazione ai [partner federati in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Si desidera consentire agli utenti di comunicare con provider federati SIP che consentono la comunicazione con provider pubblici?**

Configurare le impostazioni come descritto negli argomenti Configurare i criteri per controllare l'accesso degli utenti [pubblici,](external-access-policies/configure-policies-to-control-public-user-access.md)Abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica [e](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)Creare o modificare provider [federati SIP pubblici](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Si desidera consentire agli utenti di comunicare con provider federati SIP ospitati che eseguono Microsoft 365 o Office 365 e Skype for Business Online?**

Configurare le impostazioni come descritto negli argomenti Abilitare o disabilitare la federazione e la connettività [di](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) messaggistica istantanea pubblica e Creare o modificare provider [federati SIP ospitati.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**La distribuzione è configurata in un dominio suddiviso (anche detto ibrido), in cui il server principale di alcuni utenti si trova in una distribuzione locale mentre per altri utenti il server principale è configurato in un ambiente online?**

Configurare le impostazioni come descritto negli argomenti Configure [policies to control federated user access,](external-access-policies/configure-policies-to-control-federated-user-access.md) [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e Create or [edit hosted SIP federated providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


È possibile configurare impostazioni di accesso utente esterno, includendo tutti i criteri che si desidera utilizzare per controllare l'accesso utente esterno, anche se l'accesso utente esterno non è stato abilitato per l'organizzazione. Tuttavia, i criteri e altre impostazioni configurati dall'utente hanno effetto solo quando l'accesso utente esterno è abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso utente esterno è disabilitato o non sono configurati criteri di accesso utente esterno per supportarlo.

La distribuzione di server perimetrali autentica i tipi di utenti esterni (ad eccezione degli utenti anonimi che vengono autenticati mediante l'ID conferenza e una passkey inviati ai partecipanti anonimi quando si crea la conferenza e si invitano i partecipanti) e controlla l'accesso in base alla configurazione del supporto perimetrale. Per controllare le comunicazioni, è possibile configurare uno o più criteri e impostazioni che definiscono la modalità di comunicazione tra gli utenti all'interno e all'esterno della distribuzione. Tali criteri e impostazioni includono i criteri globali predefiniti per l'accesso degli utenti esterni, oltre ai criteri per siti e utenti che è possibile creare e configurare per abilitare uno o più tipi di accesso degli utenti esterni per siti o utenti specifici.

