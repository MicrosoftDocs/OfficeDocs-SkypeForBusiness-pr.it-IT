---
title: "Lync Server 2013: gestione della federazione e dell'accesso esterno a Skype for Business Server"
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: È possibile abilitare e configurare l'accesso degli utenti esterni per controllare se gli utenti esterni supportati possono collaborare con gli utenti Skype for Business Server interni.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676218"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestione della federazione e dell'accesso esterno a Skype for Business Server

La distribuzione di un server perimetrale o di un pool di server perimetrali è il primo passaggio per il supporto degli utenti esterni. Per informazioni dettagliate sulla distribuzione di server Perimetrali, vedere [Distribuire server perimetrali in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Dopo aver installato e configurato la distribuzione interna di Skype for Business Server, gli utenti interni dell'organizzazione possono collaborare con altri utenti interni che hanno account SIP nella Active Directory Domain Services (AD DS). La collaborazione può includere l'invio e la ricezione di messaggi istantanei, l'aggiornamento delle informazioni sulla presenza e la partecipazione a conferenze, anche note come "riunioni". È possibile abilitare e configurare l'accesso degli utenti esterni per controllare se gli utenti esterni supportati possono collaborare con gli utenti Skype for Business Server interni. Gli utenti esterni possono includere utenti remoti della distribuzione, utenti federati (inclusi gli utenti supportati dei provider di servizi di messaggistica istantanea pubblica) e partecipanti anonimi alle conferenze.

Se la distribuzione include un server perimetrale Skype for Business Server o un pool perimetrale, l'ambito dei possibili tipi di comunicazione viene notevolmente esteso. Sono disponibili molte opzioni per l'accesso utente esterno, la comunicazione con i membri di altri domini federati SIP e i provider federati SIP. Dopo aver configurato il server perimetrale o il pool perimetrale, abilitare i tipi di accesso utente esterno e configurare i criteri per controllare l'accesso esterno. In Skype for Business Server è possibile abilitare e configurare l'accesso utente esterno e i criteri usando il Skype for Business Server Pannello di controllo, Skype for Business Server [Management Shell](../management-shell.md) o entrambi.

> [!IMPORTANT]
> Quando si progettano la configurazione e i criteri per l'accesso utente esterno, è necessario conoscere la precedenza dei criteri e la modalità di applicazione degli stessi. Skype for Business Server impostazioni dei criteri applicate a un livello di criteri può sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

Per impostazione predefinita, nessun criterio supporta l'accesso utente esterno (incluso l'accesso utente remoto e l'accesso utente federato), anche se è già stato abilitato il supporto dell'accesso utente esterno per l'organizzazione. Per controllare l'uso dell'accesso utente esterno, è necessario configurare uno o più criteri. Nei criteri seguenti viene specificato il tipo di accesso utente esterno supportato:

- **Criteri globali**: i criteri globali vengono creati quando si distribuiscono i server perimetrali. Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni. Per supportare l'accesso utente esterno a livello globale, configurare i criteri globali per supportare uno o più tipi di accesso utente esterno. I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali. Se si eliminano i criteri globali, questi non vengono rimossi, ma ne vengono ripristinate le impostazioni predefinite.

- **Criteri sito**: è possibile creare e configurare uno o più criteri del sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nei criteri del sito sostituisce i criteri globali, ma solo per il sito specifico coperto dai criteri del sito. Per impostazione predefinita, i criteri del sito vengono applicati a tutti gli utenti del sito, ma i criteri utente per ignorare le impostazioni dei criteri del sito.

- **Criteri utente**: è possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso utente remoto a utenti specifici. La configurazione nei criteri utente sostituisce i criteri globali e del sito, ma solo per gli utenti specifici a cui è assegnato il criterio. Se si creano criteri utente, è necessario applicarli a uno o più utenti affinché diventino attivi.

Per stabilire quali impostazioni di configurazione e quali criteri è necessario creare o modificare, considerare gli aspetti seguenti:

**Si desidera offrire agli utenti interni ed esterni del dominio la possibilità di collaborare tramite le funzionalità di messaggistica istantanea, Web Conferencing e audio/video?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [Configurare i criteri per controllare gli accessi degli utenti remoti](external-access-policies/configure-policies-to-control-remote-user-access.md) e [abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Si desidera consentire agli utenti anonimi di partecipare ed essere invitati a conferenze ospitate da utenti inclusi nella distribuzione?**

Configurare le impostazioni come descritto nell'argomento [Assegnare criteri di conferenza per supportare utenti anonimi](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [Creare criteri di conferenza](../conferencing/create-policies.md).

**Si desidera consentire agli utenti di comunicare con i contatti dei domini federati SIP?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [Configurare i criteri per controllare l'accesso degli utenti federati](external-access-policies/configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [gestire i domini federati SIP per l'organizzazione](sip-domains/manage-sip-federated-domains-for-your-organization.md).

**Se è stata abilitata la comunicazione con i domini federati SIP, si vuole abilitare l'individuazione automatica della federazione SIP?**

Configurare le impostazioni come descritto nell'argomento [Abilitare o disabilitare l'individuazione dei partner federativi](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Se le comunicazioni con i domini federati SIP sono state abilitate, si desidera abilitare l'invio di una dichiarazione di non responsabilità ai contatti federati per avvisarli che è in uso l'archiviazione e che le comunicazioni potrebbero essere archiviate?**

Configurare le impostazioni come descritto nell'argomento [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità di archiviazione ai partner federati in](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) .

**Si vuole consentire agli utenti di comunicare con i provider federati SIP che consentono la comunicazione con i provider pubblici?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [Configurare i criteri per controllare l'accesso degli utenti pubblici](external-access-policies/configure-policies-to-control-public-user-access.md), [abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare provider federati SIP pubblici](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**Consentire agli utenti di comunicare con i provider federati SIP ospitati che eseguono Microsoft 365 o Office 365 e Skype for Business Online?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [Abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [Creare o modificare provider federati SIP ospitati](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**La distribuzione è configurata in un dominio suddiviso (anche detto ibrido), in cui il server principale di alcuni utenti si trova in una distribuzione locale mentre per altri utenti il server principale è configurato in un ambiente online?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [Configurare i criteri per controllare l'accesso degli utenti federati](external-access-policies/configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la federazione e la connettività di messaggistica istantanea pubblica](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare i provider federati SIP ospitati](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

È possibile configurare le impostazioni di accesso utente esterno anche se non è stato abilitato l'accesso utente esterno per l'organizzazione. Tuttavia, i criteri e altre impostazioni configurati dall'utente hanno effetto solo quando l'accesso utente esterno è abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti quando l'accesso utente esterno è disabilitato o se non sono configurati criteri di accesso utente esterni per supportarlo.

La distribuzione perimetrale autentica i tipi di utenti esterni e controlla l'accesso in base alla configurazione del supporto edge. L'eccezione a questa regola sono gli utenti anonimi, autenticati dall'ID conferenza e una passkey inviata al partecipante anonimo quando si crea la conferenza e si invitano i partecipanti. Per controllare la comunicazione, è possibile configurare uno o più criteri che definiscono il modo in cui gli utenti all'interno e all'esterno dell'organizzazione comunicano tra loro. I criteri e le impostazioni includono i criteri globali predefiniti, i criteri del sito e i criteri utente che è possibile creare e configurare.
