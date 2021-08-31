---
title: Routing diretto - Connessione di dispositivi analogici
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo articolo per informazioni su come usare i dispositivi analogici con Telefono Microsoft System Direct Routing.
ms.openlocfilehash: 083c5dd5b577e319a9e5308a4ec3630614254628
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733495"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Come usare i dispositivi analogici con Sistema telefonico Direct Routing

Questo articolo descrive come usare i dispositivi analogici con Sistema telefonico routing diretto. Per connettere dispositivi analogici a Routing diretto, è necessario usare un adattatore di telefonia analogica (ATA) e questo adattatore deve essere supportato dal fornitore SBC (Session Border Controller) certificato. 

Quando un utente effettua una chiamata da un dispositivo analogico, la segnalazione e i supporti passano attraverso l'adattatore di telefonia analogica (ATA) fino a SBC.  L'SBC invia la chiamata a un endpoint Microsoft Teams o alla rete PSTN (Public Switched Telephone Network) in base alla tabella di routing interna.  Quando un dispositivo effettua una chiamata, il percorso necessario dipende dai criteri di routing creati per il dispositivo.

Nel diagramma seguente il routing diretto è configurato in modo che tutte le chiamate Teams da e verso i numeri compresi tra +1425 4XX XX XX e +1425 5XX XX XX prendano il percorso rosso (linea punteggiata) e qualsiasi chiamata PSTN da e verso numeri compresi tra +1425 4XX XX XX e qualsiasi altro numero ad eccezione dell'intervallo di numeri +1425 5XX XX XX deve assumere il percorso blu (linea continua). 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra la configurazione del routing diretto.](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Esempio: Come configurare l'uso di dispositivi analogici con Routing diretto

Per configurare l'uso di dispositivi analogici con Routing diretto, è necessario connettere l'adattatore di telefonia analogica all'SBC e configurare SBC in modo che funzioni con il routing diretto. 

Questo esempio illustra i passaggi seguenti:

1. Connessione da SBC a Routing diretto.
2. Creare l'utilizzo PSTN.
3. Creare una route vocale e associarla all'uso PSTN.
4. Assegnare la route vocale all'uso PSTN.
5. Abilitare l'utente online.
6. Assegnare i criteri della route vocale all'utente.
7. Creare un percorso vocale per un dispositivo analogico.

Per informazioni su come connettere un ATA a un SBC e configurare SBC, vedere la guida alla configurazione del produttore SBC:

- [Documentazione sulla configurazione di AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Documentazione sulla configurazione della barra multifunzione](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Documentazione sulla configurazione di Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Passaggio 1.  Connessione da SBC a Routing diretto

Il comando seguente configura la connessione SBC nel modo seguente:

- Fqdn sbc.contoso.com
- Porta di segnalazione 5068
- Modalità bypass multimediale
- Informazioni sulla cronologia delle chiamate inoltrate all'SBC-
- Intestazione P-Asserted-Identity (PAI) inoltrata insieme alla chiamata 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Passaggio 2: Creare l'utilizzo PSTN 

Il comando successivo crea un utilizzo PSTN vuoto. Gli utilizzi PSTN online sono valori stringa usati per l'autorizzazione delle chiamate. Un utilizzo PSTN online collega un criterio vocale online a una route. Questo esempio aggiunge la stringa "Interop" all'elenco corrente degli utilizzi PSTN disponibili. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Passaggio 3: Creare una route vocale e associarla all'utilizzo PSTN:

Questo comando crea una nuova route vocale online con l'identità "analog-interop" per l'intervallo di numeri +1425 XXX XX XX.  La route vocale è applicabile a un elenco di gateway online sbc.contoso.com e associa la route all'uso pstn online "Interoperabilità". Una route vocale include un'espressione regolare che identifica quali numeri di telefono verranno instradati attraverso una determinata route vocale:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Passaggio 4: Assegnare la route vocale all'utilizzo PSTN:

Questo comando crea un nuovo criterio di routing vocale online per utente con l'identità "AnalogInteropPolicy". A questo criterio viene assegnato un singolo utilizzo PSTN online: "Interoperabilità".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Passaggio 5: Abilitare l'utente online

Questo comando modifica l'account utente con l'exampleuser@contoso.com. In questo caso, l'account viene modificato per abilitare VoIP aziendale, l'implementazione Microsoft di VoIP, con la segreteria telefonica abilitata e assegna il numero +142550000000 a questo utente.  Questo comando deve essere eseguito per ogni Teams utente (esclusi gli utenti di dispositivi ATA) nel tenant della società.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Passaggio 6: Assegnare i criteri della route vocale a un utente

Questo comando assegna il criterio di routing vocale online per utente AnalogInteropPolicy all'utente con l'identità exampleuser@contoso.com.  Questo comando deve essere eseguito per ogni Teams utente (esclusi gli utenti di dispositivi ATA) nel tenant della società.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Passaggio 7: Creare un percorso vocale per un dispositivo analogico

Questo comando crea una route vocale online con identità "analog-interop" per l'intervallo di numeri +1425 4XX XX XX applicabile a un elenco di gateway online sbc.contoso.com e la associa all'utilizzo pstn online "Interoperabilità".  Questo comando deve essere eseguito per ogni dispositivo analogico con un modello di numero di telefono appropriato. In alternativa, è possibile usare un modello di numero appropriato per i dispositivi analogici durante la configurazione della route vocale online durante uno dei passaggi precedenti.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Considerazioni

- Se non diversamente specificato, un dispositivo analogico è qualsiasi dispositivo in grado di inviare cifre DTMF per eseguire una chiamata. Ad esempio, telefoni analogici, fax e pager in testa.

- I telefoni analogici collegati a un ATA non possono essere cercati Teams. Teams gli utenti devono immettere manualmente il numero di telefono associato al dispositivo per chiamare il dispositivo.  
 

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
