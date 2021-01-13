---
title: "Lync Server 2013: gestione della Federazione e dell'accesso esterno a Skype for Business Server"
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
localization_priority: Normal
description: È possibile abilitare e configurare l'accesso utente esterno per controllare se gli utenti esterni supportati possono collaborare con gli utenti interni di Skype for Business Server.
ms.openlocfilehash: df8ca25dcaffb9ee563691eb327dc9ea6e9a229c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826606"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestione della Federazione e dell'accesso esterno a Skype for Business Server

La distribuzione di un server perimetrale o di un pool di server perimetrali è il primo passaggio per il supporto degli utenti esterni. Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere [Deploy Edge Server in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Dopo l'installazione e la configurazione della distribuzione interna di Skype for Business Server, gli utenti interni dell'organizzazione possono collaborare con altri utenti interni che dispongono di account SIP nei servizi di dominio Active Directory (AD DS). La collaborazione può includere l'invio e la ricezione di messaggi istantanei, l'aggiornamento delle informazioni sulla presenza e la partecipazione a conferenze, anche note come "riunioni". È possibile abilitare e configurare l'accesso utente esterno per controllare se gli utenti esterni supportati possono collaborare con gli utenti interni di Skype for Business Server. Gli utenti esterni possono includere gli utenti remoti della distribuzione, gli utenti federati (compresi gli utenti supportati dei provider di servizi di messaggistica istantanea pubblica) e i partecipanti anonimi nelle conferenze.

Se la distribuzione include l'installazione di un server perimetrale di Skype for Business Server o di un pool Edge, l'ambito dei possibili tipi di comunicazione è notevolmente esteso con una serie di opzioni per l'accesso degli utenti esterni, la comunicazione con i membri di altri domini federati SIP e i provider federati SIP. Dopo aver configurato il server perimetrale o il pool di Edge, è possibile abilitare i tipi di accesso utente esterno che si desidera fornire e configurare i criteri per il controllo dell'accesso esterno. In Skype for Business Server, è possibile abilitare e configurare l'accesso e i criteri per gli utenti esterni utilizzando il pannello di controllo di Skype for Business Server, [Skype for Business Server Management Shell](../management-shell.md)o entrambi, in base ai requisiti di attività. 



> [!IMPORTANT]  
> Quando si progettano la configurazione e i criteri per l'accesso utente esterno, è necessario conoscere la precedenza dei criteri e la modalità di applicazione degli stessi. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sovrascrivere le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.


Per impostazione predefinita, non vengono configurati criteri per supportare l'accesso utente esterno, incluso l'accesso di utenti remoti e di utenti federati, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'utilizzo dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Sono inclusi i criteri di accesso esterno seguenti:

  - **Criteri globali**   Il criterio globale viene creato quando si distribuiscono i server perimetrali. Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare i criteri globali in modo da supportare uno o più tipi di opzioni di accesso degli utenti esterni. I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali. Se si eliminano i criteri globali, questi non vengono rimossi, ma ne vengono ripristinate le impostazioni predefinite.

  - **Criteri sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.

  - **Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso utente remoto a utenti specifici. La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente. Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici. Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.

Per stabilire quali impostazioni di configurazione e quali criteri è necessario creare o modificare, considerare gli aspetti seguenti:

**Si desidera offrire agli utenti interni ed esterni del dominio la possibilità di collaborare tramite le funzionalità di messaggistica istantanea, Web Conferencing e audio/video?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Remote User accesso](external-access-policies/configure-policies-to-control-remote-user-access.md), e [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Si desidera consentire agli utenti anonimi di partecipare ed essere invitati a conferenze ospitate da utenti inclusi nella distribuzione?**

Configurare le impostazioni come descritto nell'argomento [assegnazione dei criteri di conferenza per supportare gli utenti anonimi](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [creare criteri di conferenza](../conferencing/create-policies.md).

**Si desidera consentire agli utenti di comunicare con i contatti dei domini federati SIP?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Federated User Access](external-access-policies/configure-policies-to-control-federated-user-access.md), [Enable or Disable Federation and Public IM Connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Manage SIP federato Domains for Your Organization](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Se è stata abilitata la comunicazione con i domini federati SIP, si desidera abilitare l'individuazione automatica della Federazione SIP?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'individuazione dei partner federativi](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Se le comunicazioni con i domini federati SIP sono state abilitate, si desidera abilitare l'invio di una dichiarazione di non responsabilità ai contatti federati per avvisarli che è in uso l'archiviazione e che le comunicazioni potrebbero essere archiviate?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'invio di una dichiarazione di non responsabilità di archiviazione per i partner federati in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Si desidera consentire agli utenti di comunicare con i provider federati SIP che consentono la comunicazione con i provider pubblici?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control public User Access](external-access-policies/configure-policies-to-control-public-user-access.md), [Enable or Disable Federation and Public IM Connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Create or Edit public SIP Federated Providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Si desidera consentire agli utenti di comunicare con i provider federati SIP che sono provider ospitati che eseguono Microsoft 365 o Office 365 e Skype for business online?**

Configurare le impostazioni come descritto negli argomenti [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare provider federati SIP ospitati](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**La distribuzione è configurata in un dominio suddiviso (anche detto ibrido), in cui il server principale di alcuni utenti si trova in una distribuzione locale mentre per altri utenti il server principale è configurato in un ambiente online?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Federated User Access](external-access-policies/configure-policies-to-control-federated-user-access.md), [Enable or Disable Federation and Public IM Connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e [Create or Edit Hosted SIP Federated Providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


È possibile configurare impostazioni di accesso utente esterno, includendo tutti i criteri che si desidera utilizzare per controllare l'accesso utente esterno, anche se l'accesso utente esterno non è stato abilitato per l'organizzazione. Tuttavia, i criteri e altre impostazioni configurati dall'utente hanno effetto solo quando l'accesso utente esterno è abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso utente esterno è disabilitato o non sono configurati criteri di accesso utente esterno per supportarlo.

La distribuzione di server perimetrali autentica i tipi di utenti esterni (ad eccezione degli utenti anonimi che vengono autenticati mediante l'ID conferenza e una passkey inviati ai partecipanti anonimi quando si crea la conferenza e si invitano i partecipanti) e controlla l'accesso in base alla configurazione del supporto perimetrale. Per controllare le comunicazioni, è possibile configurare uno o più criteri e impostazioni che definiscono la modalità di comunicazione tra gli utenti all'interno e all'esterno della distribuzione. Tali criteri e impostazioni includono i criteri globali predefiniti per l'accesso degli utenti esterni, oltre ai criteri per siti e utenti che è possibile creare e configurare per abilitare uno o più tipi di accesso degli utenti esterni per siti o utenti specifici.

