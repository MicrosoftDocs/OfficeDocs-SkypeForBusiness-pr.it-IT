---
title: Pianificare la connessione ibrida | Integrazione di Skype for Business Server 2019 e Microsoft 365 o Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Pianificare l'implementazione della connettività ibrida tra Skype for Business Server e Teams o Skype for Business online configurando la modalità ibrida di Skype for Business.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 1a43243f4b5ce827a7c688c1aad1983466aa6ca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110262"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come pianificare la connettività ibrida tra Skype for Business Server e Teams o Skype for Business online. La configurazione della connettività ibrida è il primo passaggio per spostare l'ambiente locale nel cloud.

Se sono presenti utenti di Skype for Business locale che usano anche Teams (in modo affiancato), tali utenti non avranno la possibilità di interagire con gli utenti di Skype for Business dal client Teams, né di comunicare con gli utenti di organizzazioni federate dal client Teams. Per ottenere questa funzionalità in Teams, questi utenti devono essere spostati da Skype for Business locale al cloud, operazione che richiede la configurazione della modalità ibrida di Skype for Business. Inoltre, per un'esperienza ottimale, questi utenti devono essere in modalità Solo Teams, in modo da garantire che tutte le chiamate e le chat in arrivo provenienti da qualsiasi utente siano presenti nel client Teams dell'utente.

È anche necessario configurare la connettività ibrida e spostare tutti gli utenti nel cloud prima di rimuovere la distribuzione locale di Skype for Business.  Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti nel cloud in base alla pianificazione e alle esigenze aziendali. Grazie al routing diretto è possibile sfruttare l'infrastruttura vocale locale durante lo spostamento nel cloud e dopo il completamento della migrazione.

In questo argomento vengono descritti i requisiti di infrastruttura e di sistema necessari per configurare la connettività ibrida tra la distribuzione di Skype for Business Server locale esistente e Teams o Skype for Business online.

Dopo aver letto questo argomento ed essere pronti per configurare la connettività ibrida, vedere Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md) Negli argomenti di configurazione vengono fornite istruzioni dettagliate per la configurazione della connettività ibrida tra la distribuzione locale e Teams o Skype for Business online.

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>Informazioni sulla funzionalità Spazio indirizzi SIP condiviso

<a name="BKMK_Overview"> </a>

 Con la connettività ibrida impostata tra una distribuzione locale di Skype for Business Server e Teams o Skype for Business online, è possibile avere alcuni utenti ospitati in locale e alcuni utenti ospitati online.

Questo tipo di configurazione si basa sulla funzionalità dello spazio di indirizzi SIP condiviso e talvolta viene definito "dominio diviso", ovvero gli utenti di un dominio, ad esempio contoso.com, sono suddivisi tra l'utilizzo di Skype for Business Server in locale e Teams o Skype for Business online, come illustrato nel diagramma seguente:

![Connettività ibrida di Skype for Business - dominio diviso](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando è configurato lo spazio di indirizzi SIP condiviso:

- Azure Active Directory Connect viene usato per sincronizzare la directory locale con Microsoft 365 o Office 365.
- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti ospitati online possono interagire con Skype for Business Online o i servizi di Teams.
- Gli utenti di entrambi gli ambienti possono comunicare tra loro.
- Active Directory locale è autorevole. Tutti gli utenti devono essere creati prima in Active Directory locale e quindi sincronizzati con Azure AD. Anche se si intende ospitare l'utente online, è necessario prima creare l'utente nell'ambiente locale e quindi spostarlo online per assicurarsi che l'utente sia individuabile dagli utenti locali.

Prima che un utente possa essere spostato online, all'utente deve essere assegnata una licenza skype for business online (piano 2). Se l'utente utilizza Teams, all'utente deve essere assegnata anche una licenza di Teams (e la licenza di Skype for Business deve rimanere abilitata). Se gli utenti desiderano sfruttare funzionalità online aggiuntive, ad esempio Audioconferenza o Sistema telefonico, è necessario assegnare loro la licenza appropriata in Microsoft 365 o Office 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisiti dell'infrastruttura di connettività ibrida

<a name="BKMK_Infrastructure"> </a>

Per implementare la connettività ibrida tra l'ambiente locale e i servizi di comunicazione di Microsoft 365 o Office 365, è necessario soddisfare i requisiti di infrastruttura seguenti:

- Una singola distribuzione locale di Skype for Business Server o Lync Server distribuita in una topologia supportata. Vedere [Requisiti di topologia](plan-hybrid-connectivity.md#BKMK_Topology) in questo argomento.

- Un'organizzazione di Microsoft 365 o Office 365 con Skype for Business online abilitato.
    > [!NOTE]
    > È possibile usare un solo tenant per una configurazione ibrida con la distribuzione locale.
    
- Azure Active Directory Connect per sincronizzare la directory locale con Microsoft 365 o Office 365. Per ulteriori informazioni, vedere [Azure AD Connect: Account e autorizzazioni.](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Strumenti di amministrazione di Skype for Business Server. Questi elementi sono necessari per spostare gli utenti dall'ambiente locale al cloud. Questi strumenti devono essere installati in un server con accesso sia alla distribuzione locale che a Internet.
- Strumenti di amministrazione online. Puoi usare l'interfaccia di amministrazione di Teams o Windows PowerShell per gestire Teams e Skype for Business online. Per usare PowerShell per gestire Teams o Skype for Business online, scaricare e installare il connettore skype for business online.
- Lo spazio di indirizzi SIP condiviso deve essere abilitato e la distribuzione locale deve essere configurata per l'utilizzo di Microsoft 365 o Office 365 come provider di hosting. Per ulteriori informazioni sui passaggi necessari per configurare la connettività ibrida, vedere [Configure hybrid connectivity](configure-hybrid-connectivity.md).

Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti in Teams o Skype for Business online. Per ulteriori informazioni, vedere Spostare gli utenti da locale [a Teams](move-users-from-on-premises-to-teams.md) e Spostare gli utenti da locale a Skype for [Business online.](move-users-from-on-premises-to-skype-for-business-online.md)

## <a name="server-version-requirements"></a>Requisiti di versione del server

<a name="BKMK_Topology"> </a>

Per configurare la distribuzione ibrida con **Teams o Skype for Business online,** è necessario disporre di una delle topologie supportate seguenti:

- Distribuzione di Skype for Business Server 2019 con tutti i server che eseguono Skype for Business Server 2019.
- Distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.
- Distribuzione di Lync Server 2013 con tutti i server che eseguono Lync Server 2013.  Tuttavia, se è necessaria la connettività vocale ibrida, è necessario utilizzare una topologia con versione mista, come indicato di seguito.
- Una distribuzione con un massimo di 2 diverse versioni del server, come elencato di seguito:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

Se si desidera la voce ibrida *in* qualsiasi topologia, sia il server perimetrale designato come server perimetrale federativo che il pool associato alla federazione SIP devono eseguire Skype for Business 2015 o versione successiva. Gli utenti possono rimanere in un pool di Lync 2013, se ne esiste uno. Per ulteriori dettagli, vedere [Plan Phone System with PSTN Connectivity in Skype for Business Server.](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md)

Le topologie seguenti che includono **Lync Server 2010** sono supportate con Skype for Business online per la messaggistica istantanea e le riunioni. Le topologie che includono **Lync Server 2010 non sono supportate per** la voce ibrida o Teams.

- Distribuzione mista di Lync Server 2010 e Skype for Business Server 2015
- Distribuzione mista di Lync Server 2010 e Lync Server 2013
- Distribuzione di Lync Server 2010 con tutti i server che eseguono Lync Server 2010 con gli aggiornamenti cumulativi più recenti.

Il server perimetrale federativo e il server hop successivo dal server perimetrale federativo devono eseguire Lync Server 2010 con gli aggiornamenti cumulativi più recenti. Gli Strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o in una workstation di gestione.

## <a name="multi-forest-support"></a>Supporto multiforesta

<a name="BKMK_MultiForest"> </a>

Microsoft supporta i seguenti tipi di scenari ibridi a più foreste:

- **Topologia della foresta di risorse.** In questo tipo di topologia esiste una foresta che ospita Skype for Business Server (la foresta delle risorse) e una o più foreste aggiuntive che ospitano le identità degli account, che accedono a Skype for Business Server nella foresta di risorse. In generale, gli utenti possono accedere alle funzionalità di Skype for Business in un'altra foresta se vengono soddisfatti i requisiti seguenti:
  - Gli utenti vengono sincronizzati correttamente nella foresta che ospita Skype for Business. Nelle configurazioni ibride, ciò significa che gli utenti devono essere sincronizzati come oggetti utente disabilitati.
  - La foresta che ospita Skype for Business deve considerare attendibile la foresta contenente gli utenti.
    Per informazioni dettagliate sugli scenari ibridi della foresta di risorse, vedere [Deploy a resource forest topology for hybrid Skype for Business.](configure-a-multi-forest-environment-for-hybrid.md)

- **Più distribuzioni di Skype for Business Server in più foreste.** Questa configurazione può derivare da scenari di fusione e acquisizione, nonché in aziende più complesse. Il consolidamento di tutti gli utenti dall'ambiente locale al cloud in una singola organizzazione di Microsoft 365 o Office 365 può essere raggiunto per qualsiasi organizzazione con più distribuzioni skype for business, purché siano soddisfatti i requisiti chiave seguenti:
  - Deve essere coinvolta al massimo un'organizzazione di Microsoft 365 o Office 365. Il consolidamento in scenari con più organizzazioni non è supportato.
  - In un determinato momento, solo una foresta Skype for Business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste di Skype for Business locali devono rimanere completamente locali (e presumibilmente federate tra loro). Si noti che queste altre organizzazioni locali possono eseguire la sincronizzazione con AAD se lo si desidera con nuove funzionalità per disabilitare i domini [SIP online](/powershell/module/skype/disable-csonlinesipdomain) disponibili a partire da dicembre 2018.

    I clienti con distribuzioni di Skype for Business in più foreste devono eseguire la migrazione completa di ogni foresta Di Skype for Business singolarmente nell'organizzazione di Microsoft 365 o Office 365 utilizzando la funzionalità split domain (Shared SIP Address Space) e quindi disabilitare la distribuzione ibrida con la distribuzione locale, prima di passare alla migrazione della successiva distribuzione di Skype for Business locale. Inoltre, prima di essere migrati nel cloud, gli utenti locali rimangono in uno stato federato con tutti gli utenti non rappresentati nella directory locale dello stesso utente. Per altri dettagli, vedi [Consolidamento del cloud per Teams e Skype for Business.](cloud-consolidation.md)

## <a name="federation-requirements"></a>Requisiti di federazione

<a name="BKMK_Federation"> </a>

Quando si configura la modalità ibrida di Skype for Business, è necessario verificare che gli ambienti locali e online possano essere federati tra loro.  Per impostazione predefinita, l'ambiente online ha una federazione aperta. L'ambiente locale spesso ha chiuso la federazione per impostazione predefinita.  

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

- La corrispondenza del dominio deve essere configurata nello stesso modo per la distribuzione locale e per l'organizzazione di Microsoft 365 o Office 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la federazione aperta per l'organizzazione online. Se l'individuazione partner non è abilitata, la federazione chiusa deve essere configurata per l'organizzazione online.
- L'elenco Domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco Domini bloccati per il tenant online.
- L'elenco Domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco Domini consentiti per il tenant online.
- La federazione deve essere abilitata per le comunicazioni esterne per il tenant online.

## <a name="network-considerations"></a>Considerazioni sulla rete

Nelle sezioni seguenti vengono descritte le considerazioni relative a:

- Impostazioni DNS
- Considerazioni sul firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Impostazioni DNS per le distribuzioni ibride

<a name="BKMK_DNS"> </a>

Quando si creano record DNS per distribuzioni ibride, tutti i record DNS esterni di Skype for Business devono puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, fare riferimento ai [requisiti DNS per Skype for Business Server.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

Inoltre, è necessario verificare che la risoluzione DNS descritta nella tabella seguente funzioni nella distribuzione locale. Se è già stata configurata la federazione per l'ambiente locale, è probabile che siano già presenti.

|Record DNS  <br/> |Risolvibile da  <br/> |Requisito DNS  <br/> |
|:-----|:-----|:-----|
|Record DNS SRV per _sipfederationtls._tcp.\<sipdomain.com\> per tutti i domini SIP supportati per la risoluzione degli IP esterni di Access Edge  <br/> |Server perimetrali  <br/> |Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP diviso tra locale e online.  <br/> Deve utilizzare una corrispondenza rigida dei nomi DNS tra il dominio nel nome utente e il record SRV.  <br/> |
|Record A DNS per l'FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com la risoluzione degli IP esterni di Web Conferencing Edge  <br/> |Computer degli utenti connessi alla rete aziendale interna  <br/> |Consentire agli utenti online di presentare o visualizzare il contenuto nelle riunioni ospitate in locale. Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.  <br/> |

A seconda della configurazione del DNS nell'organizzazione, potrebbe essere necessario aggiungere questi record alla zona DNS ospitata interna per i domini SIP corrispondenti per fornire la risoluzione DNS interna a tali record.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerazioni sul firewall per le distribuzioni ibride

<a name="BKMK_Firewall"> </a>

I computer della rete devono essere in grado di eseguire ricerche DNS Internet standard. Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del data center di Microsoft Online Services, è inoltre necessario configurare i dispositivi firewall di rete in modo che accettino connessioni basate su nomi di dominio con caratteri jolly,ad esempio tutto il traffico proveniente da \* .outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni dei nomi con caratteri jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Per ulteriori informazioni, inclusi i dettagli sulle porte e i requisiti di protocollo, vedere URL e intervalli di indirizzi IP di [Microsoft 365 e Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)