---
title: Routing diretto-connessione di dispositivi analogici
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo articolo per informazioni su come usare i dispositivi analogici con il routing diretto di Microsoft Phone System.
ms.openlocfilehash: 525e898bd0eafe88d6893249465734d7c33a10b2
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341796"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Come usare i dispositivi analogici con routing diretto del sistema telefonico

Questo articolo descrive come usare i dispositivi analogici con il routing diretto del sistema telefonico. Per connettere i dispositivi analogici al routing diretto, è necessario usare un adattatore per la telefonia analogica (ATA) e questo adattatore deve essere supportato dal fornitore della sessione certificata border controller (SBC). 

Quando un utente effettua una chiamata da un dispositivo analogico, la segnalazione e il flusso multimediale attraverso l'adattatore di telefonia analogica (ATA) a SBC.  Il SBC Invia la chiamata a un endpoint di Microsoft teams o alla rete PSTN (Public Switched Telephone Network) in base alla tabella di routing interna.  Quando un dispositivo effettua una chiamata, la route che impiega dipende dai criteri di routing creati per il dispositivo.

Nel diagramma seguente viene configurato il routing diretto in modo che tutti i team chiamate da e verso i numeri compresi tra + 1425 4XX XX XX e + 1425 5XX XX XX debbano eseguire la route rossa (linea tratteggiata) e qualsiasi chiamata PSTN da e verso i numeri compresi tra + 1425 4XX XX XX e qualsiasi altro numero eccetto  intervallo di numeri + 1425 5XX XX XX deve prendere la route blu (linea continua). 

![Diagramma che mostra la configurazione del routing diretto](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Esempio: come configurare l'uso di dispositivi analogici con routing diretto

Per configurare l'uso di dispositivi analogici con routing diretto, è necessario connettere l'adattatore di telefonia analogica a SBC e configurare SBC per l'utilizzo del routing diretto. 

In questo esempio vengono illustrati i passaggi seguenti:

1. Connettere il SBC al routing diretto
2. Creare l'utilizzo PSTN
3. Creare una route vocale e associarla all'utilizzo PSTN
4. Assegnare la route vocale all'utilizzo PSTN
5. Abilitare l'utente online
6. Assegnare il criterio della route vocale all'utente
7. Creare una route vocale per un dispositivo analogico

Per informazioni su come connettere un ATA a un SBC e configurare il SBC, vedere la guida alla configurazione del produttore SBC:
- [Documentazione di configurazione di AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Passaggio 1.  Connettere il SBC al routing diretto

Il comando seguente configura la connessione SBC come indicato di seguito:

- FQDN sbc.contoso.com
- Porta di segnalazione 5068
- Modalità bypass multimediale
- Informazioni sulla cronologia delle chiamate inoltrate a SBC-
- Intestazione P-Asserted-Identity (PAI) inoltrata insieme alla chiamata 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Passaggio 2: creare l'utilizzo PSTN 

Il comando successivo crea un uso PSTN vuoto. Gli usi PSTN online sono valori stringa usati per l'autorizzazione di chiamata. Un uso PSTN online collega un criterio vocale online a una route. Questo esempio aggiunge la stringa "Interop" all'elenco corrente degli usi PSTN disponibili. 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Passaggio 3: creare una route vocale e associarla all'utilizzo PSTN:

Questo comando crea una nuova route vocale online con l'identità "interoperabilità analogica" per l'intervallo di numeri + 1425 XXX XX XX.  La route vocale è applicabile a un elenco di gateway online sbc.contoso.com e associa la route con l'utilizzo PSTN online "Interop". Una route vocale include un'espressione regolare che identifica i numeri di telefono che verranno instradati tramite una determinata route vocale:

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Passaggio 4: assegnare la route vocale all'utilizzo PSTN:

Questo comando crea un nuovo criterio di routing vocale per utente online con l'identità "AnalogInteropPolicy". A questo criterio viene assegnato un singolo utilizzo PSTN online: "Interop".

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Passaggio 5: abilitare l'utente online

Questo comando consente di modificare l'account utente con Identity exampleuser@contoso.com. In questo caso, l'account viene modificato per abilitare Enterprise Voice, l'implementazione Microsoft del VoIP, con la segreteria telefonica abilitata e assegna il numero + 14255000000 a questo utente.  Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant della società.

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Passaggio 6: assegnare il criterio della route vocale a un utente

Questo comando assegna all'utente il criterio di routing vocale online per utente AnalogInteropPolicy con l'identità exampleuser@contoso.com.  Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant della società.

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Passaggio 7: creare una route vocale per un dispositivo analogico

Questo comando crea una route vocale online con Identity "Analog-Interop" per l'intervallo di numeri + 1425 4XX XX XX applicabile a un elenco di gateway online sbc.contoso.com e lo associa all'utilizzo PSTN online "Interop".  Questo comando deve essere eseguito per ogni dispositivo analogico con il modello di numero di telefono appropriato. In alternativa, è possibile usare un modello di numero appropriato per i dispositivi analogici durante la configurazione della route vocale online durante uno dei passaggi precedenti.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Considerazioni

- Se non diversamente specificato, un dispositivo analogico è un dispositivo che può inviare cifre DTMF per effettuare una chiamata. Ad esempio, telefoni analogici, fax e pagine generali.
- I telefoni analogici collegati a un ATA non possono essere cercati da teams. Gli utenti di teams devono immettere manualmente il numero di telefono associato al dispositivo per chiamare il dispositivo.  
 

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
