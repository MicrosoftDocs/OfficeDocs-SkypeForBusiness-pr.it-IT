---
title: Ottimizzazione dei media locali di routing diretto
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
description: Configurare l'ottimizzazione multimediale locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121606"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurare l'ottimizzazione multimediale locale per il routing diretto

La configurazione per l'ottimizzazione media locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, ad esempio routing basato sulla posizione e chiamate di emergenza dinamiche. Per altre informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere [impostazioni di rete per le funzionalità di cloud Voice](cloud-voice-network-settings.md).

Prima di configurare l'ottimizzazione multimediale locale, vedere [ottimizzazione dei contenuti multimediali locali per il routing diretto](direct-routing-media-optimization.md).  

Per configurare l'ottimizzazione multimediale locale, sono necessarie le operazioni seguenti. Puoi usare l'interfaccia di amministrazione di teams o PowerShell. Per informazioni dettagliate, vedere [gestire la topologia di rete](manage-your-network-topology.md).

1. Configurare l'utente e i siti SBC (come descritto in questo articolo).
2. Configurare la SBCs for local Media Optimization (in base alla specifica del fornitore SBC).

Il diagramma seguente mostra la configurazione della rete usata negli esempi in questo articolo.

![Diagramma che mostra la configurazione della rete per gli esempi](media/direct-routing-media-op-9.png "Configurazione di rete per gli esempi")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurare l'utente e i siti SBC

Per configurare l'utente e i siti SBC, sarà necessario:

1. [Gestire indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).  

2. [Definire la topologia di rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.

3. [Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando SBC (s) ai siti con le modalità pertinenti e i valori del proxy SBC.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurare SBC per l'ottimizzazione di elementi multimediali locali in base alla specifica del fornitore SBC

Questo articolo descrive la configurazione per i componenti Microsoft. Per informazioni sulla configurazione di SBC, vedere la documentazione del fornitore SBC.

L'ottimizzazione media locale è supportata dai seguenti fornitori di SBC:

| Fornitore | Prodotto |    Versione software |
|:------------|:-------|:-------| :-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    SBC 500 medium |   7.20 a. 256 | 
|            |  SBC 800 Medium |   7.20 a. 256 | 
|            |  SBC 2600 medium |  7.20 a. 256 | 
|            |  SBC 4000 medium |  7.20 a. 256 | 
|            |  SBC 1000B medium | 7.20 a. 256 | 
|            |  SBC 9000 medium |  7.20 a. 256 | 
|            |  SBC virtuale per edizioni medious |   7.20 a. 256 | 
|            |  SBC Cloud Edition | 7.20 a. 256 |
| [Core SBC della barra multifunzione](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8,2  |
|            |  SBC 5210         | 8,2  |
|            |  SBC 5400         | 8,2  |
|            |  SBC 7000         | 8,2  |
|            |  SBC SWe          | 8,2  |
| [Bordo SBC della barra multifunzione](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 (Build 239) |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 + |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Gestire indirizzi IP attendibili esterni

Gli IPs attendibili esterni sono gli IPs esterni Internet della rete aziendale. Questi IP sono gli indirizzi IP usati dai client Microsoft teams quando si connettono a Microsoft 365. È necessario aggiungere questi IP esterni per ogni sito in cui sono presenti utenti che usano l'ottimizzazione media locale.

Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress. Puoi definire un numero illimitato di indirizzi IP attendibili per un tenant. Se gli IPs esterni visti da Microsoft 365 sono sia indirizzi IPv4 che IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP. Per IPv4, USA Mask 32. Per IPv6, USA mask 128. È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterni specificando diversi MaskBits nel cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Esempio di aggiunta di indirizzi IP attendibili.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definire la topologia di rete

Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia di rete.

Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.  Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.

### <a name="define-network-regions"></a>Definire le aree di rete

Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion. Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni. Il <site ID> parametro CentralSite è facoltativo.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

L'esempio seguente crea un'area di rete denominata APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definire i siti di rete

Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite. Ogni sito di rete deve essere associato a un'area di rete.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definire le subnet di rete

Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet. Ogni subnet di rete può essere associata a un solo sito. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definire la topologia di rete virtuale 

Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway.
L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenere presente quanto segue: 
   - Se il cliente ha un singolo SBC, il parametro-ProxySBC deve essere obbligatorio $null o il valore FQDN di SBC (SBC centrale con lo scenario Trunks centralizzato).
   - Il parametro-MediaBypass deve essere impostato su $true per supportare l'ottimizzazione dei contenuti multimediali locali.
   - Se SBC non ha il set di parametri-BypassMode, le intestazioni X-MS non verranno inviate. 
   - Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.  Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.

L'esempio seguente aggiunge tre SBCs ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Ignora sempre:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Nota: per garantire che le operazioni ininterrotte quando vengono configurate l'ottimizzazione media locale e il routing basato sulla posizione (LBR), SBCs downstream debba essere abilitato per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC downstream. Questa impostazione non è obbligatoria per il proxy SBC.

In base alle informazioni fornite sopra, il routing diretto includerà tre intestazioni SIP proprietarie per SIP invita e invita nuovamente come illustrato nella tabella seguente.

Intestazioni X-MS introdotte in routing diretto su invita e invita nuovamente se BypassMode è definito:

| Nome intestazione | Valori | Commenti | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interno/esterno | Indica se l'utente è interno o esterno |
| Request-URI invita SIP: + 84439263000@VNsbc.contoso.com SIP/2,0 | FQDN DI SBC | Il nome di dominio completo che è destinato alla chiamata anche se SBC non è connesso direttamente al routing diretto |
| X-MS-MediaPath | Esempio: proxysbc.contoso.com, VNsbc.contoso.com | Ordine di SBCs che deve essere usato per il percorso multimediale tra l'utente e il SBC di destinazione. Il SBC finale è sempre l'ultima volta |
| X-MS-UserSite | usersiteID | Stringa definita dall'amministratore del tenant |

## <a name="call-flows"></a>Flussi delle chiamate 

Di seguito sono illustrati i flussi delle chiamate per due modalità:

- [Ignorare sempre](#always-bypass-mode)
- [Solo per gli utenti locali](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modalità di bypass sempre

La modalità Ignora sempre è l'opzione più semplice da configurare. L'amministratore del tenant può configurare un singolo sito per tutti gli utenti e SBCs se tutti i SBCs sono raggiungibili da qualsiasi sito.

Gli esempi mostrano sempre la modalità di bypass per gli scenari seguenti:

- [Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chiamate in uscita e l'utente è esterno](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Chiamate in ingresso e l'utente è esterno](#inbound-calls-and-the-user-is-external-with-always-bypass)

La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:

| FQDN | Indirizzo IP esterno SBC | Indirizzo IP interno SBC | Subnet interna | Posizione | NAT esterno (IP attendibile) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Nessuno | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Nessuno | 192.168.2.5 | 192.168.2.0/24 | Indonesia | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapore | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con bypass sempre

| Modalità |    Utente |  Posizione |  Direzione chiamata |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interno |  Lo stesso sito di SBC |  Outbound |

La tabella seguente mostra la configurazione e l'azione degli utenti finali:

| Posizione fisica dell'utente| L'utente effettua o riceve una chiamata a/da numero | Numero di telefono dell'utente  | Criteri di routing vocale online | Modalità configurata per SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 | + 84 4 5555 5555   | Priorità 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorità 2:. *-proxysbc.contoso.com   | VNsbc.contoso.com-ignora sempre <br> proxysbc.contoso.com-ignora sempre


Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità di bypass sempre e l'utente nella stessa posizione di SBC.

![Diagramma che mostra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")

La tabella seguente mostra le intestazioni X-MS inviate tramite routing diretto:

| Parametro | Spiegazione |
|:------------|:-------|
| Invitare + 8443926300@VNsbc.contoso.com | Il nome di dominio completo di destinazione dell'oggetto SBC definito nei criteri di routing vocale online viene inviato nell'URI della richiesta | 
| X-MS-UserLocation: Internal | Il campo indica che l'utente si trova all'interno della rete aziendale |
| X-MS-MediaPath: VNsbc.contoso.com |   Specifica il SBC che deve essere attraversato dal client al SBC di destinazione. In questo caso, come abbiamo sempre bypassare, e il client è interno il nome di destinazione inviato come unico nome nell'intestazione. | 
|X-MS-UserSite: Vietnam |   Campo indicato nel sito in cui si trova l'utente. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Le chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC con il bypass sempre

| Modalità |    Utente |  Posizione |  Direzione chiamata |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interno | Lo stesso sito di SBC | In ingresso |


In una chiamata in ingresso, la posizione dell'utente è sconosciuta e il SBC deve indovinare dove si trova l'utente. Se l'ipotesi non è corretta, sarà necessario un nuovo invito. Questo caso presuppone che l'utente sia interno, che l'elemento multimediale possa fluire direttamente e che non siano necessarie altre azioni (re-INVITE).
Il SBC connesso al servizio di routing diretto riporta la posizione del SBC di origine fornendo campi di record-route e Contact. In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.

Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile. Il routing diretto userà sempre 180 squillare in questo caso. 

Il diagramma seguente mostra la scala SIP per la chiamata in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in uscita e l'utente è esterno con l'esclusione sempre

| Modalità |    Utente |  Sito |  Direzione chiamata
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Esterno |  N/D | Outbound |


Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-12.png)

La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:

| Parametro |   Spiegazione |
|:------------|:-------|
|Invitare + 8443926300@VNsbc.contoso.com | Il nome di dominio completo di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta.|
| X-MS-UserLocation: esterno | Il campo indica che l'utente si trova all'esterno della rete aziendale. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Specifica il SBC che deve essere attraversato dal client al SBC di destinazione. In questo caso, come abbiamo sempre bypassare, e il client è esterno. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in ingresso e l'utente è esterno con il bypass sempre

| Modalità | Utente | Sito |  Direzione chiamata |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Esterno |  N/D |   In ingresso |

Per una chiamata in ingresso, il SBC connesso al routing diretto deve inviare un re-invite (per impostazione predefinita, i candidati multimediali locali sono sempre offerti) se la posizione dell'utente è esterna.  L'X-MediaPath viene calcolato in base a record-route e all'utente SBC specificato.

Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Solo per la modalità utenti locali

I candidati multimediali locali del SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione di SBC. In tutti gli altri casi, il flusso multimediale verrà eseguito attraverso un IP interno o esterno del SBC proxy.

Vengono descritti gli scenari seguenti:

- [Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [L'utente non si trova nella stessa posizione di SBC, ma nella rete aziendale](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Le chiamate in ingresso e l'utente sono interne, ma non si trova nella stessa posizione di SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

La tabella seguente mostra la configurazione e l'azione degli utenti finali:

| Posizione fisica dell'utente |  L'utente effettua o riceve una chiamata a/da numero |  Numero di telefono dell'utente | Criteri di routing vocale online |   Modalità configurata per SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 |  + 84 4 5555 5555 | Priorità 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorità 2:. *-proxysbc.contoso.com | VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-ignora sempre |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Le chiamate in uscita e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali

| Modalità | Utente | Sito | Direzione chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno |Uguale a SBC   | Outbound |

Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC. Si tratta dello stesso flusso visualizzato nelle [chiamate in uscita quando l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Le chiamate in ingresso e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali

| Modalità | Utente | Sito | Direzione chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno | Uguale a SBC | In ingresso |

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC. Si tratta dello stesso flusso illustrato nelle [chiamate in ingresso quando l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>L'utente non si trova nella stessa posizione di SBC, ma è nella rete aziendale solo per gli utenti locali

| Modalità | Utente | Sito |Direzione chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interno |   Diverso da SBC | Outbound |

Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.


Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamata in ingresso e l'utente è interno, ma non è nella stessa posizione dell'SBC con solo per gli utenti locali

| Modalità |    Utente |  Sito |  Direzione chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interno |    Diverso da SBC |    In ingresso |

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-17.png)









