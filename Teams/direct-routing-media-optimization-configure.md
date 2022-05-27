---
title: Configurare Ottimizzazione multimediale locale per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurare Ottimizzazione multimediale locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674878"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurare Ottimizzazione multimediale locale per il routing diretto

La configurazione per Ottimizzazione multimediale locale si basa su impostazioni di rete comuni ad altre funzionalità vocali nel cloud, ad esempio Location-Based Routing e chiamate di emergenza dinamiche. Per altre informazioni su aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedi [Impostazioni di rete per le funzionalità vocali nel cloud](cloud-voice-network-settings.md).

Prima di configurare Ottimizzazione multimediale locale, vedi [Ottimizzazione multimediale locale per il routing diretto](direct-routing-media-optimization.md).

Per configurare Ottimizzazione multimediale locale, sono necessari i passaggi seguenti. È possibile usare il Centro Teams Amministrazione o PowerShell. Per informazioni dettagliate, vedere [Gestire la topologia di rete](manage-your-network-topology.md).

1. Configurare l'utente e i siti SBC, come descritto in questo articolo.
2. Configurare gli SBC per Ottimizzazione multimediale locale (in base alle specifiche del fornitore SBC).

Il diagramma seguente illustra la configurazione della rete usata negli esempi di questo articolo.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra la configurazione della rete per alcuni esempi.](media/direct-routing-media-op-9.png "Configurazione della rete per esempi")

## <a name="configure-the-user-and-the-sbc-sites"></a>Configurare l'utente e i siti SBC

Per configurare l'utente e i siti SBC, è necessario:

1. [Gestire indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).

2. [Definire la topologia della rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.

3. [Definire la topologia della rete virtuale](#define-the-virtual-network-topology) assegnando SBC ai siti con le modalità pertinenti e i valori SBC proxy.

> [!NOTE]
> Ottimizzazione multimediale locale si basa sulle posizioni client rilevate come esterne o interne rispetto alle reti aziendali con portata a un'interfaccia interna del controller dei confini della sessione (SBC) di Routing diretto (DR).
> Negli scenari di VPN con tunnel diviso quando l'endpoint client viene rilevato come esterno alla rete del cliente, Microsoft segnalerà la posizione esterna alla rete SBC anche se il client può raggiungere l'interfaccia interna della SBC per il routing diretto del cliente. I clienti che utilizzano Ottimizzazione multimediale locale potrebbero riscontrare tempi prolungati di configurazione delle chiamate e, in alcuni casi, non ricevere audio quando ricevono chiamate da PSTN.
> Per evitare questo errore, gli amministratori VPN devono bloccare l'accesso tra gli utenti VPN remoti e l'interfaccia interna SBC direct Routing.

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurare SBC per Ottimizzazione multimediale locale in base alle specifiche del fornitore di SBC

Questo articolo descrive la configurazione per i componenti Microsoft. Per informazioni sulla configurazione di SBC, vedere la documentazione del fornitore di SBC. Per informazioni sui fornitori di SBC che supportano Ottimizzazione multimediale locale, vedere [Session Border Controllers Certified for Direct Routing](direct-routing-border-controllers.md).

## <a name="manage-external-trusted-ip-addresses"></a>Gestire indirizzi IP attendibili esterni

Gli IP esterni attendibili sono gli IP esterni di Internet della rete aziendale. Questi IP sono gli indirizzi IP usati dai client Microsoft Teams quando si connettono a Microsoft 365. È necessario aggiungere questi IP esterni per ogni sito in cui gli utenti usano Ottimizzazione multimediale locale.

Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress. È possibile definire un numero illimitato di indirizzi IP attendibili per un tenant. Se gli IP esterni visualizzati da Microsoft 365 sono indirizzi IPv4 e IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP. Per IPv4, usare la maschera 32. Per IPv6, usare la maschera 128. È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterne specificando MaskBits diversi nel cmdlet.

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

Esempio di aggiunta di indirizzi IP attendibili.

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>Definire la topologia della rete

In questa sezione viene descritto come definire le aree di rete, i siti di rete e le subnet di rete per la topologia della rete.

Tutti i parametri fanno distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso caso usato durante l'installazione.  Ad esempio, i valori GatewaySiteID "Vietnam" e "vietnam" verranno trattati come siti diversi.

### <a name="define-network-regions"></a>Definire le aree di rete

Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion. Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni. Il parametro CentralSite `<site ID>` è facoltativo.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

Nell'esempio seguente viene creata un'area di rete denominata APAC:

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>Definire siti di rete

Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite. Ogni sito di rete deve essere associato a un'area di rete.

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definire subnet di rete

Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet. Ogni subnet di rete può essere associata a un solo sito.

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>Definire la topologia della rete virtuale

Innanzitutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway.
L'amministratore tenant definisce la topologia della rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenere presente quanto segue:

- Se il cliente ha un singolo SBC, il parametro -ProxySBC deve essere obbligatorio $null o il valore FQDN SBC (scenario SBC centrale con trunk centralizzati).
- Il parametro -MediaBypass deve essere impostato su $true per supportare Ottimizzazione multimediale locale.
- Se SBC non ha il parametro -BypassMode impostato, le intestazioni X-MS non verranno inviate.
- Tutti i parametri fanno distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso caso usato durante l'installazione.  Ad esempio, i valori GatewaySiteID "Vietnam" e "vietnam" verranno trattati come siti diversi.

L'esempio seguente aggiunge tre SBC ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Bypass sempre:

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> Per garantire il funzionamento senza interruzioni quando ottimizzazione multimediale locale e Location-Based routing (LBR) sono configurati contemporaneamente, è necessario abilitare le SBC a valle per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC a valle. Questa impostazione non è obbligatoria per il server SBC proxy.

In base alle informazioni precedenti, Direct Routing includerà tre intestazioni SIP proprietarie per inviti SIP e inviti di nuovo, come illustrato nella tabella seguente.

Intestazioni X-MS introdotte in Routing diretto sugli inviti e Re-Invites se BypassMode è definito:

|Nome intestazione|Valori|Commenti|
|---|---|---|
|X-MS-UserLocation|interno/esterno|Indica se l'utente è interno o esterno|
|Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0|SBC FQDN|Fqdn assegnato alla chiamata anche se l'SBC non è direttamente connesso al routing diretto|
|X-MS-MediaPath|Esempio: proxysbc.contoso.com, VNsbc.contoso.com|Ordine degli SBC che devono essere usati per il percorso multimediale tra l'utente e la scheda SBC di destinazione. La scheda SBC finale è sempre ultima|
|X-MS-UserSite|usersiteID|Stringa definita dall'amministratore del tenant|

## <a name="call-flows"></a>Flussi delle chiamate

Di seguito sono illustrati i flussi delle chiamate per due modalità:

- [Ignora sempre](#always-bypass-mode)
- [Solo per gli utenti locali](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Ignora sempre la modalità

La modalità Bypass sempre è l'opzione più semplice da configurare. L'amministratore del tenant può configurare un singolo sito per tutti gli utenti e gli SBC se tutti gli SBC sono raggiungibili da qualsiasi sito.

Gli esempi mostrano la modalità Bypass sempre per gli scenari seguenti:

- [Chiamate in uscita e l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chiamate in ingresso e l'utente si trova nella stessa posizione della scheda SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chiamate in uscita e l'utente è esterno](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Chiamate in ingresso e l'utente è esterno](#inbound-calls-and-the-user-is-external-with-always-bypass)

La tabella seguente mostra il nome di dominio completo e gli indirizzi IP usati negli esempi:

|FQDN|Indirizzo IP esterno SBC|Indirizzo IP interno SBC|Subnet interna|Posizione|NAT esterno (IP attendibile)|
|---|---|---|---|---|---|
|VNsbc.contoso.com|Nessuno|192.168.1.5|192.168.1.0/24|Vietnam|172.16.240.110|
|IDsbc.contoso.com|Nessuno|192.168.2.5|192.168.2.0/24|Indonesia|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|Singapore|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Chiamate in uscita e l'utente si trova nella stessa posizione di SBC con Ignora sempre

|Modalità|Utente|Posizione|Direzione chiamata|
|---|---|---|---|
|AlwaysBypass|Interno|Lo stesso sito di SBC|Outbound|

La tabella seguente mostra la configurazione e l'azione dell'utente finale:

|Posizione fisica dell'utente|L'utente effettua o riceve una chiamata a/da numero|Numero di telefono dell'utente|Criteri di routing vocale online|Modalità configurata per SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926 3000|+84 4 5555 5555|Priorità 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com|VNsbc.contoso.com - Ignora sempre <br> proxysbc.contoso.com - Ignora sempre|

Il diagramma seguente illustra la scala SIP per una chiamata in uscita con la modalità Bypass sempre e l'utente nella stessa posizione di SBC.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra le chiamate in uscita.](media/direct-routing-media-op-10.png "Chiamate in uscita")

La tabella seguente mostra le intestazioni X-MS inviate da Direct Routing:

|Parametro|Spiegazione|
|---|---|
|Invita +8443926300@VNsbc.contoso.com|L'FQDN di destinazione del server SBC, come definito nei criteri di routing vocale online, viene inviato nell'URI richiesta|
|X-MS-UserLocation: interno|Il campo indica che l'utente si trova all'interno della rete aziendale|
|X-MS-MediaPath: VNsbc.contoso.com|Specifica quale SBC il client deve attraversare fino alla SBC di destinazione. In questo caso come abbiamo Sempre Bypass, e il client è interno il nome di destinazione inviato come l'unico nome nell'intestazione.|
|X-MS-UserSite: Vietnam|Campo indicato all'interno del sito in cui si trova l'utente.|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Chiamate in ingresso e l'utente si trova nella stessa posizione di SBC con Ignora sempre

|Modalità|Utente|Posizione|Direzione chiamata|
|---|---|---|---|---|
|AlwaysBypass|Interno|Lo stesso sito di SBC|Inbound|

In una chiamata in ingresso, la posizione dell'utente è sconosciuta e SBC deve indovinare dove si trova l'utente. Se l'ipotesi non è corretta, sarà necessario un nuovo invito. In questo caso si presuppone che l'utente sia interno, che gli elementi multimediali possano scorrere direttamente e che non siano necessarie altre azioni (invita di nuovo).
Il servizio SBC connesso al servizio Routing diretto segnala la posizione SBC di origine fornendo i campi Record-Route e Contatto. In base a questi campi, il percorso multimediale viene calcolato dal routing diretto.

Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile. In questo caso, il routing diretto userà sempre 180 suoneria.

Il diagramma seguente mostra la scala SIP per le chiamate in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra la scala SIP.](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in uscita e l'utente è esterno con Ignora sempre

|Modalità|Utente|Sito|Direzione chiamata
|---|---|---|---|
|AlwaysBypass|Esterno|N/D|Outbound|

Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:

> [!div class="mx-imgBorder"]
> ![Il diagramma mostra la scala SIP.](media/direct-routing-media-op-12.png)

La tabella seguente mostra le intestazioni X-MS inviate dal servizio Direct Routing:

|Parametro|Spiegazione|
|---|---|
|Invita +8443926300@VNsbc.contoso.com|L'FQDN di destinazione del server SBC, come definito nei criteri di routing vocale online, viene inviato nell'URI richiesta.|
|X-MS-UserLocation: esterno|Il campo indica che l'utente si trova all'esterno della rete aziendale.|
|X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com|Specifica quale SBC il client deve attraversare fino alla SBC di destinazione. In questo caso come abbiamo Sempre Bypassare, e il client è esterno.|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in ingresso e l'utente è esterno con Ignora sempre

|Modalità|Utente|Sito|Direzione chiamata|
|---|---|---|---|
|AlwaysBypass|Esterno|N/D|Inbound|

Per una chiamata in ingresso, la SBC connessa al routing diretto deve inviare di nuovo l'invito (per impostazione predefinita, i candidati multimediali locali sono sempre offerti) se la posizione dell'utente è esterna.  X-MediaPath viene calcolato in base a Record-Route e all'utente SBC specificato.

Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra di nuovo la scala SIP.](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>Solo per la modalità utenti locali

I candidati per contenuti multimediali locali della scheda SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione del servizio SBC.Local media candidates of the target SBC will will offered only if a user is in the same location as the SBC. In tutti gli altri casi, i contenuti multimediali fluiranno attraverso un indirizzo IP interno o esterno del server SBC proxy.

Vengono descritti gli scenari seguenti:

- [Chiamate in uscita e l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Chiamate in ingresso e l'utente si trova nella stessa posizione della scheda SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [L'utente non si trova nella stessa posizione dell'SBC, ma si trova nella rete aziendale](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Le chiamate in ingresso e l'utente è interno, ma non si trova nella stessa posizione di SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

La tabella seguente mostra la configurazione e l'azione dell'utente finale:

|Posizione fisica dell'utente|L'utente effettua o riceve una chiamata a/da numero|Numero di telefono dell'utente|Criteri di routing vocale online|Modalità configurata per SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926  3000|+84 4 5555 5555|Priorità 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com|VNsbc.contoso.com - Proxysbc.contoso.com OnlyForLocalUsers - Ignora sempre|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamate in uscita e l'utente si trova nella stessa posizione di SBC con Solo per gli utenti locali

|Modalità|Utente|Sito|Direzione chiamata|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Uguale a SBC|Outbound|

Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC. Questo è lo stesso flusso visualizzato nelle [chiamate in uscita quando l'utente si trova nella stessa posizione del servizio SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![Il diagramma mostra di nuovo la scala SIP.](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamate in ingresso e l'utente si trova nella stessa posizione di SBC con Solo per gli utenti locali

|Modalità|Utente|Sito|Direzione chiamata|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Uguale a SBC|Inbound|

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC. Si tratta dello stesso flusso visualizzato nelle [chiamate in ingresso quando l'utente si trova nella stessa posizione del servizio di posta elettronica in](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass) ingresso.

> [!div class="mx-imgBorder"]
> ![Un altro diagramma che mostra la scala SIP.](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>L'utente non si trova nella stessa posizione dell'SBC, ma si trova nella rete aziendale con Solo per gli utenti locali

|Modalità|Utente|Sito|Direzione chiamata|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Diverso da SBC|Outbound|

Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.

Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione dell'SBC.

> [!div class="mx-imgBorder"]
> ![Un altro diagramma mostra la scala SIP.](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamata in ingresso e l'utente è interno, ma non si trova nella stessa posizione di SBC con Solo per gli utenti locali

|Modalità|Utente|Sito|Direzione chiamata|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Diverso da SBC|Inbound|

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione dell'SBC.

> [!div class="mx-imgBorder"]
> ![Un altro diagramma che mostra la scala SIP.](media/direct-routing-media-op-17.png)
