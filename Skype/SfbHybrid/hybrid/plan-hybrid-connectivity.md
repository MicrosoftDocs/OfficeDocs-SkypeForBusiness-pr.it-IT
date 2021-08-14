---
title: Pianificare la connettività ibrida | Skype for Business Server e Teams
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
description: Pianificare l'implementazione della connettività ibrida tra Skype for Business Server e Teams configurando la Skype for Business ibrida.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 090aab3d376a228915779c8bf55864484cee715d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234051"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Pianificare la connettività ibrida tra Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Leggere questo argomento per informazioni su come pianificare la connettività ibrida tra Skype for Business Server e Teams. La configurazione della connettività ibrida è il primo passaggio per spostare l'ambiente locale nel cloud.

Se sono presenti utenti di Skype for Business locale che usano anche Teams (in modo affiancato), tali utenti non avranno la possibilità di interagire con gli utenti di Skype for Business dal client Teams, né di comunicare con gli utenti di organizzazioni federate dal client Teams. Per ottenere questa funzionalità in Teams, questi utenti devono essere spostati da Skype for Business locale al cloud, operazione che richiede la configurazione della modalità ibrida di Skype for Business. Inoltre, per un'esperienza ottimale, questi utenti devono essere in modalità Solo Teams, che garantisce che tutte le chiamate e le chat in arrivo provenienti da qualsiasi utente si atterrino nel client di Teams dell'utente.

È anche necessario configurare la connettività ibrida e spostare tutti gli utenti nel cloud prima di rimuovere la distribuzione locale di Skype for Business.  Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti nel cloud in base alla pianificazione e alle esigenze aziendali. Grazie al routing diretto è possibile sfruttare l'infrastruttura vocale locale durante lo spostamento nel cloud e dopo il completamento della migrazione.

In questo argomento vengono descritti l'infrastruttura e i requisiti di sistema necessari per configurare la connettività ibrida tra la distribuzione locale Skype for Business Server locale e Teams.

Dopo aver letto questo argomento e aver configurato la connettività ibrida, vedere [Configure hybrid connectivity between Skype for Business Server and Teams](configure-hybrid-connectivity.md). Negli argomenti di configurazione vengono fornite istruzioni dettagliate per la configurazione della connettività ibrida tra la distribuzione locale e Teams.

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

## <a name="implications-of-the-upcoming-retirement-of-skype-for-business-online"></a>Implicazioni del ritiro imminente di Skype for Business Online
È importante ricordare che sia prima che dopo il ritiro di Skype for Business Online, gli utenti ospitati in Skype for Business Server locale possono usare Teams, ma non possono essere TeamsOnly. Per impostazione predefinita, gli utenti sono in modalità Isole. Gli utenti possono sperimentare tutti i vantaggi di Teams, in particolare la federazione e il supporto PSTN, solo quando sono in modalità TeamsOnly. 

Il ritiro imminente di Skype for Business Online non ha alcun impatto sul ciclo di vita del supporto esistente di Skype for Business Server o Lync Server 2013.  Tuttavia, il ritiro imminente di Skype for Business Online inciderà su alcuni aspetti del modo in cui i clienti con Skype for Business Server locale o Lync Server 2013, incluse le organizzazioni ibride esistenti, passano al cloud. Ciò che non cambierà dopo il ritiro è che l'uso della distribuzione ibrida come mezzo per la transizione dall'ambiente locale al cloud rimane invariato.

Attualmente e fino al ritiro di Skype for Business Online, le organizzazioni ibride possono essere costituite da tre tipi di utenti di base: 
- Utenti locali (che possono o non possono usare Teams, ma non in Teams modalità Solo utenti) 
- Utenti online con qualsiasi modalità di coesistenza diversa da TeamsOnly
- TeamsOnly users.

Dopo il ritiro di Skype for Business Online, tuttavia, le organizzazioni ibride possono essere costituite solo da due tipi di utenti di base: 
- Utenti locali (Who possono o meno usare Teams, ma non in modalità TeamsOnly)
- Teams Solo utenti. 

Perché le organizzazioni si spostino da Skype for Business Server o Lync Server 2013 a Teams, devono comunque configurare e configurare la distribuzione ibrida utilizzando lo stesso set di strumenti, esattamente come prima del *ritiro.* Ciò che è cambiato è che quando si sposta un utente da locale a Teams, non è più necessario specificare il passaggio per spostare gli utenti direttamente da locale a `-MoveToTeams` `Move-CsUser` TeamsOnly. In precedenza, se questa opzione non è stata specificata, gli utenti passavano da Skype for Business Server locale a Skype for Business Online e la loro modalità rimaneva invariata. In preparazione del ritiro, quando si sposta un utente da locale al cloud con , agli utenti viene automaticamente assegnata la modalità TeamsOnly e le riunioni da locale vengono convertite automaticamente Teams riunioni, come se fosse stato specificato il commutatore, indipendentemente dal fatto che il commutatore sia effettivamente `Move-CsUser` `-MoveToTeams` specificato. Sono incluse le migrazioni da Lync Server 2013, che non hanno mai avuto il `MoveToTeams` passaggio. 

Analogamente, se un nuovo utente viene creato direttamente in Microsoft 365 anziché in locale, l'utente avrà automaticamente la modalità Solo Teams indipendentemente dalla modalità del tenant. Questo comportamento verrà implementazione nel prossimo futuro con il ritiro. Tenere presente che in un'organizzazione ibrida, i nuovi utenti devono essere creati in Active Directory locale (e quindi sincronizzati in Microsoft 365), anziché creare direttamente un utente in Microsoft 365, per garantire che gli utenti locali possano instradare il nuovo utente.

Le modalità di coesistenza continueranno ad esistere dopo il ritiro di Skype for Business Online. Come in precedenza, agli utenti con account ospitati in Skype for Business Server locale può essere assegnata qualsiasi modalità di coesistenza ad eccezione di TeamsOnly. Dopo il ritiro, tuttavia, gli utenti ospitati online possono essere solo TeamsOnly (a differenza del presente in cui gli utenti di Skype for Business Online possono essere in qualsiasi modalità).  

> [!Important]
> - Le organizzazioni ibride esistenti con utenti ospitati in Skype for Business Online che non sono TeamsOnly dovrebbero concentrarsi sull'aggiornamento di questi utenti alla modalità Solo Teams il prima possibile, ma non oltre il ritiro il 31 luglio 2021. Se nell'organizzazione sono ancora presenti utenti ospitati in Skype for Business Online che non sono TeamsOnly, è possibile che venga pianificato un aggiornamento assistito da Microsoft per la transizione di questi utenti a TeamsOnly. Ciò non inciderà sugli utenti ospitati in Skype for Business Server locale. Le notifiche di pianificazione verranno inviate in anticipo ai clienti ibridi con utenti ospitati in Skype for Business Online prima che questi utenti online non di TeamsOnly siano aggiornati a Teams.
> - In preparazione del ritiro di Skype for Business Online, non sarà più possibile assegnare una modalità diversa da TeamsOnly a un utente che si trova online.

## <a name="about-shared-sip-address-space-functionality"></a>Informazioni sulla funzionalità Spazio indirizzi SIP condiviso

<a name="BKMK_Overview"> </a>

 Con la connettività ibrida impostata tra una distribuzione locale di Skype for Business Server e Teams, è possibile avere alcuni utenti ospitati in locale e alcuni utenti ospitati online.

Questo tipo di configurazione si basa sulla funzionalità dello spazio di indirizzi SIP condiviso e talvolta viene definito "dominio diviso", ovvero gli utenti di un dominio, ad esempio contoso.com, vengono suddivisi tra l'utilizzo di Skype for Business Server locale e Teams, come illustrato nel diagramma seguente:

![Skype for Business Hybrid connettività - dominio diviso](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando è configurato lo spazio di indirizzi SIP condiviso:

- Azure Active Directory Connessione viene usato per sincronizzare la directory locale con Microsoft 365.
- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti ospitati online possono interagire con Teams e, fino al 31 luglio 2021, Skype for Business Online in base alla modalità di coesistenza.
- Gli utenti di entrambi gli ambienti possono comunicare tra loro.
- Active Directory locale è autorevole. Tutti gli utenti devono essere creati prima in Active Directory locale e quindi sincronizzati con Azure AD. Anche se si desidera che l'utente sia disponibile online, è necessario prima creare l'utente nell'ambiente locale e quindi spostare l'utente in linea per assicurarsi che l'utente sia individuabile dagli utenti locali.

Prima che un utente possa essere spostato online, all'utente deve essere assegnata una licenza Teams e Skype for Business Online (Piano 2). **L'assegnazione della licenza Skype for Business Online è necessaria anche dopo il ritiro di Skype for Business Online.** Se gli utenti desiderano sfruttare funzionalità online aggiuntive, ad esempio Audioconferenza o Sistema telefonico, è necessario assegnare loro la licenza appropriata in Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisiti dell'infrastruttura di connettività ibrida

<a name="BKMK_Infrastructure"> </a>

Per implementare la connettività ibrida tra l'ambiente locale e i servizi di comunicazione Microsoft 365, è necessario soddisfare i requisiti di infrastruttura seguenti:

- Una singola distribuzione locale di Skype for Business Server o Lync Server distribuita in una topologia supportata. Vedere [Requisiti di topologia](plan-hybrid-connectivity.md#BKMK_Topology) in questo argomento.

- Organizzazione Microsoft 365 con Teams.
    > [!NOTE]
    > È possibile usare un solo tenant per una configurazione ibrida con la distribuzione locale.
    
- Azure Active Directory Connessione sincronizzare la directory locale con Microsoft 365. Per ulteriori informazioni, vedere [Azure AD Connessione: Account e autorizzazioni](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server strumenti di amministrazione. Questi elementi sono necessari per spostare gli utenti dall'ambiente locale al cloud. Questi strumenti devono essere installati in un server con accesso sia alla distribuzione locale che a Internet.
- Strumenti di amministrazione online. Puoi usare l'interfaccia di Teams o Windows PowerShell per gestire Teams. Per usare PowerShell per gestire Teams, scaricare e installare il modulo Teams PowerShell. (Il Skype for Business Online Connector è stato ritirato).
- Lo spazio di indirizzi SIP condiviso deve essere abilitato e la distribuzione locale deve essere configurata per l'utilizzo Microsoft 365 come provider di hosting. Per ulteriori informazioni sui passaggi necessari per configurare la connettività ibrida, vedere [Configure hybrid connectivity](configure-hybrid-connectivity.md).

Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti in Teams. Per ulteriori informazioni, vedere [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Requisiti di versione del server

<a name="BKMK_Topology"> </a>

Per configurare la distribuzione ibrida **con Teams**, è necessario disporre di una delle topologie supportate seguenti:

- Distribuzione di Skype for Business Server 2019 con tutti i server che eseguono Skype for Business Server 2019.
- Distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.
- Distribuzione di Lync Server 2013 con tutti i server che eseguono Lync Server 2013.  Tuttavia, se è necessaria la connettività vocale ibrida, è necessario utilizzare una topologia con versione mista, come indicato di seguito.
- Una distribuzione con un massimo di 2 diverse versioni del server, come elencato di seguito:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

Se si desidera la voce ibrida *in* qualsiasi topologia, sia il server perimetrale designato come server perimetrale federativo che il pool associato alla federazione SIP devono eseguire Skype for Business 2015 o versione successiva. Gli utenti possono rimanere in un pool di Lync 2013, se ne esiste uno. Per ulteriori dettagli, vedere [Plan your voice solution](/MicrosoftTeams/cloud-voice-landing-page.md).

> [!NOTE]
> Lync Server 2010 non è supportato con Teams.

## <a name="multi-forest-support"></a>Supporto multiforesta

<a name="BKMK_MultiForest"> </a>

Microsoft supporta i seguenti tipi di scenari ibridi a più foreste:

- **Topologia della foresta di risorse.** In questo tipo di topologia esiste una foresta che ospita Skype for Business Server (la foresta di risorse) e una o più foreste aggiuntive che ospitano le identità degli account, che accedono al Skype for Business Server nella foresta di risorse. In generale, gli utenti possono accedere Skype for Business in un'altra foresta se vengono soddisfatti i requisiti seguenti:
  - Gli utenti vengono sincronizzati correttamente nella foresta che ospita Skype for Business. Nelle configurazioni ibride, ciò significa che gli utenti devono essere sincronizzati come oggetti utente disabilitati.
  - La foresta che ospita Skype for Business deve considerare attendibile la foresta contenente gli utenti.
    Per informazioni dettagliate sugli scenari ibridi della foresta di risorse, vedere [Deploy a resource forest topology for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Più distribuzioni di Skype for Business Server in più foreste.** Questa configurazione può derivare da scenari di fusione e acquisizione, nonché in aziende più complesse. Il consolidamento di tutti gli utenti dall'ambiente locale al cloud in una singola organizzazione Microsoft 365 può essere realizzato per qualsiasi organizzazione con più distribuzioni di Skype for Business, purché siano soddisfatti i requisiti chiave seguenti:
  - Deve essere coinvolta al massimo Microsoft 365'organizzazione. Il consolidamento in scenari con più organizzazioni non è supportato.
  - In un determinato momento, solo una foresta Skype for Business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste locali Skype for Business devono rimanere completamente locali (e presumibilmente federate tra loro). Si noti che queste altre organizzazioni locali possono eseguire la sincronizzazione con AAD se lo si desidera con nuove funzionalità per disabilitare i domini [SIP online](/powershell/module/skype/disable-csonlinesipdomain) disponibili a partire da dicembre 2018.

    I clienti con distribuzioni di Skype for Business in più foreste devono eseguire la migrazione completa di ogni foresta di Skype for Business singolarmente nell'organizzazione di Microsoft 365 utilizzando la funzionalità split-domain (Shared SIP Address Space). Al termine della migrazione della foresta, i clienti devono quindi disabilitare la distribuzione ibrida con la distribuzione locale prima di passare alla migrazione della successiva distribuzione Skype for Business locale. Inoltre, prima di essere migrati nel cloud, gli utenti locali rimangono in uno stato federato con tutti gli utenti non rappresentati nella directory locale dello stesso utente. Per ulteriori dettagli, vedere [Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisiti di federazione

<a name="BKMK_Federation"> </a>

Quando si configura Skype for Business ibrida, è necessario verificare che gli ambienti locali e online possano eseguire la federazione tra loro.  Per impostazione predefinita, l'ambiente online ha una federazione aperta. L'ambiente locale spesso ha chiuso la federazione per impostazione predefinita.  

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

- La corrispondenza del dominio deve essere configurata nello stesso modo per la distribuzione locale e l'organizzazione Microsoft 365 locale. Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la federazione aperta per l'organizzazione online. Se l'individuazione partner non è abilitata, la federazione chiusa deve essere configurata per l'organizzazione online.
- L'elenco Domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco Domini bloccati per il tenant online.
- L'elenco Domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco Domini consentiti per il tenant online.
- La federazione deve essere abilitata per le comunicazioni esterne per il tenant online.

## <a name="network-considerations"></a>Considerazioni sulla rete

Nelle sezioni seguenti vengono descritte le considerazioni relative a:

- Impostazioni DNS
- Considerazioni sul firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Impostazioni DNS per le distribuzioni ibride

<a name="BKMK_DNS"> </a>

Quando si creano record DNS per distribuzioni ibride, tutti Skype for Business dns esterni devono puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, fare riferimento ai [requisiti DNS per Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Inoltre, è necessario verificare che la risoluzione DNS descritta nella tabella seguente funzioni nella distribuzione locale. Se è già stata configurata la federazione per l'ambiente locale, è probabile che siano già presenti.

|Record DNS  <br/> |Risolvibile da  <br/> |Requisito DNS  <br/> |
|:-----|:-----|:-----|
|Record DNS SRV per _sipfederationtls._tcp.\<sipdomain.com\> per tutti i domini SIP supportati per la risoluzione degli IP esterni di Access Edge  <br/> |Server perimetrali  <br/> |Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP diviso tra locale e online.  <br/> Deve utilizzare una corrispondenza rigida dei nomi DNS tra il dominio nel nome utente e il record SRV.  <br/> |
|Record A DNS per l'FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com la risoluzione degli IP esterni di Web Conferencing Edge  <br/> |Computer degli utenti connessi alla rete aziendale interna  <br/> |Consentire agli utenti online di presentare o visualizzare il contenuto nelle riunioni ospitate in locale. Il contenuto PowerPoint file, lavagne, sondaggi e note condivise.  <br/> |

A seconda della configurazione del DNS nell'organizzazione, potrebbe essere necessario aggiungere questi record alla zona DNS ospitata interna per i domini SIP corrispondenti per fornire la risoluzione DNS interna a tali record.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerazioni sul firewall per le distribuzioni ibride

<a name="BKMK_Firewall"> </a>

I computer della rete devono essere in grado di eseguire ricerche DNS Internet standard. Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del data center di Microsoft Online Services, è inoltre necessario configurare i dispositivi firewall di rete in modo che accettino connessioni basate su nomi di dominio con caratteri jolly, ad esempio tutto il traffico proveniente da \* .outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni dei nomi con caratteri jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Per ulteriori informazioni, inclusi i dettagli sulle porte e sui requisiti di protocollo, vedere [Microsoft 365 URL e intervalli di indirizzi IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
