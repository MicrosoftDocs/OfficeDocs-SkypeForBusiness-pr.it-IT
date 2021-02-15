---
title: Routing diretto - Connessione di dispositivi analogici
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
description: Leggere questo articolo per informazioni su come usare i dispositivi analogici con l'instradamento diretto del sistema telefonico Microsoft.
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841487"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Come usare dispositivi analogici con l'instradamento diretto del sistema telefonico

Questo articolo descrive come usare i dispositivi analogici con l'instradamento diretto del sistema telefonico. Per connettere dispositivi analogici a routing diretto, è necessario usare un adattatore ATA (Analog Telephony Adapter) che deve essere supportato dal fornitore certificato di Session Border Controller (SBC). 

Quando un utente effettua una chiamata da un dispositivo analogico, il flusso del traffico di segnalazione e del supporto attraverso l'Adattatore per telefonia analogica (ATA) passa al sistema SBC.  SBC invia la chiamata a un endpoint di Microsoft Teams o alla rete PSTN (Public Switched Telephone Network) in base alla tabella di routing interna.  Quando un dispositivo effettua una chiamata, il percorso che effettua dipende dai criteri di routing creati per il dispositivo.

Nel diagramma seguente il routing diretto è configurato in modo che tutte le chiamate di Teams da e verso i numeri compresi tra +1425 4XX XX XX e +1425 5XX XX XX devono seguire il percorso rosso (linea punteggiata) e qualsiasi chiamata PSTN da e verso i numeri compresi tra +1425 4XX XX XX e qualsiasi altro numero ad eccezione dell'intervallo di numeri +1425 5XX XX XX deve seguire il percorso blu (linea continua). 

> [!div class="mx-imgBorder"]
> ![Diagramma che illustra la configurazione del routing diretto](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Esempio: Come configurare l'uso di dispositivi analogici con routing diretto

Per configurare l'uso di dispositivi analogici con routing diretto, è necessario connettere l'adattatore per telefonia analoga a SBC e configurare SBC per il funzionamento con il routing diretto. 

Questo esempio illustra i passaggi seguenti:

1. Connettere il servizio SBC al routing diretto.
2. Creare l'utilizzo di PSTN.
3. Creare un percorso vocale e associarlo all'utilizzo di PSTN.
4. Assegnare il percorso vocale all'utilizzo di PSTN.
5. Abilitare l'utente online.
6. Assegnare i criteri per le route vocali all'utente.
7. Creare un percorso vocale per un dispositivo analogico.

Per informazioni su come connettere un'ATA a un database SBC e configurare SBC, vedere la guida alla configurazione del produttore del servizio SBC:

- [Documentazione della configurazione AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Documentazione sulla configurazione della barra multifunzione](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Documentazione sulla configurazione di Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Passaggio 1.  Connettere il servizio SBC al routing diretto

Il comando seguente configura la connessione SBC nel modo seguente:

- Fqdn sbc.contoso.com
- Porta di segnalazione 5068
- Modalità bypass multimediale
- Informazioni sul cronologia delle chiamate inoltrate al controller SBC-
- Intestazione PAI (P-Asserted-Identity) inoltrata insieme alla chiamata 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Passaggio 2: Creare l'utilizzo di PSTN 

Il comando successivo crea un utilizzo di PSTN vuoto. Gli utilizzi PSTN online sono valori stringa usati per l'autorizzazione delle chiamate. Un utilizzo PSTN online collega un criterio vocale online a un percorso. Questo esempio aggiunge la stringa "Interoperabilità" all'elenco corrente degli utilizzi pstN disponibili. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Passaggio 3: Creare un percorso vocale e associarlo all'utilizzo di PSTN:

Questo comando crea una nuova route vocale online con l'identità "analog-interoperabilità" per l'intervallo di numeri +1425 XXX XX XX.  Il percorso vocale è applicabile a un elenco di gateway online sbc.contoso.com e associa la route all'uso online di PSTN "Interoperabilità". Un percorso vocale include un'espressione regolare che identifica i numeri di telefono che verranno instradati attraverso un determinato percorso vocale:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Passaggio 4: Assegnare la route vocale all'utilizzo di PSTN:

Questo comando crea un nuovo criterio di routing vocale online per utente con il criterio identity "AnalogInteropPolicy". A questo criterio viene assegnato un singolo utilizzo PSTN online: "Interoperabilità".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Passaggio 5: Abilitare l'utente online

Questo comando modifica l'account utente con il nome di exampleuser@contoso.com. In questo caso, l'account viene modificato per abilitare VoIP aziendale, l'implementazione Microsoft di VoIP, con la segreteria telefonica abilitata e assegna il numero +14255000000 a questo utente.  Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant aziendale.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Passaggio 6: Assegnare i criteri per le route vocali a un utente

Questo comando assegna all'utente il criterio di routing vocale per utente online AnalogInteropPolicy con l'identità exampleuser@contoso.com.  Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant aziendale.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Passaggio 7: Creare un percorso vocale per un dispositivo analogico

Questo comando crea una route vocale online con identità "interoperabilità analoga" per l'intervallo di numeri +1425 4XX XX applicabile a un elenco di gateway online sbc.contoso.com e lo associa all'uso online di PSTN "Interoperabilità".  Questo comando deve essere eseguito per ogni dispositivo analogico con il modello di numero di telefono appropriato. In alternativa, è possibile usare un modello di numero corretto per i dispositivi analogici durante la configurazione del percorso vocale online durante uno dei passaggi precedenti.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Considerazioni

- Se non diversamente specificato, un dispositivo analogico è qualsiasi dispositivo in grado di inviare cifre DTMF per eseguire una chiamata. Ad esempio, telefoni analogici, fax e pagine di sovraccarico.

- I telefoni analogici connessi a un'ATA non sono ricercabili da Teams. Gli utenti di Teams devono immettere manualmente il numero di telefono associato al dispositivo per chiamare il dispositivo.  
 

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
