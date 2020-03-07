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
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558516"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="75ee5-103">Come usare i dispositivi analogici con routing diretto del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="75ee5-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="75ee5-104">Questo articolo descrive come usare i dispositivi analogici con il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="75ee5-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="75ee5-105">Per connettere i dispositivi analogici al routing diretto, è necessario usare un adattatore per la telefonia analogica (ATA) e questo adattatore deve essere supportato dal fornitore della sessione certificata border controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="75ee5-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="75ee5-106">Quando un utente effettua una chiamata da un dispositivo analogico, la segnalazione e il flusso multimediale attraverso l'adattatore di telefonia analogica (ATA) a SBC.</span><span class="sxs-lookup"><span data-stu-id="75ee5-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="75ee5-107">Il SBC Invia la chiamata a un endpoint di Microsoft teams o alla rete PSTN (Public Switched Telephone Network) in base alla tabella di routing interna.</span><span class="sxs-lookup"><span data-stu-id="75ee5-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="75ee5-108">Quando un dispositivo effettua una chiamata, la route che impiega dipende dai criteri di routing creati per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75ee5-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="75ee5-109">Nel diagramma seguente viene configurato il routing diretto in modo che tutti i team chiamate da e verso i numeri compresi tra + 1425 4XX XX XX e + 1425 5XX XX XX debbano eseguire la route rossa (linea tratteggiata) e qualsiasi chiamata PSTN da e verso i numeri compresi tra + 1425 4XX XX XX e qualsiasi altro numero eccetto  intervallo di numeri + 1425 5XX XX XX deve prendere la route blu (linea continua).</span><span class="sxs-lookup"><span data-stu-id="75ee5-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![Diagramma che mostra la configurazione del routing diretto](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="75ee5-111">Esempio: come configurare l'uso di dispositivi analogici con routing diretto</span><span class="sxs-lookup"><span data-stu-id="75ee5-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="75ee5-112">Per configurare l'uso di dispositivi analogici con routing diretto, è necessario connettere l'adattatore di telefonia analogica a SBC e configurare SBC per l'utilizzo del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="75ee5-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="75ee5-113">In questo esempio vengono illustrati i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="75ee5-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="75ee5-114">Connettere il SBC al routing diretto.</span><span class="sxs-lookup"><span data-stu-id="75ee5-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="75ee5-115">Creare l'utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="75ee5-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="75ee5-116">Creare una route vocale e associarla all'utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="75ee5-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="75ee5-117">Assegnare la route vocale all'uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="75ee5-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="75ee5-118">Abilitare l'utente online.</span><span class="sxs-lookup"><span data-stu-id="75ee5-118">Enable the online user.</span></span>
6. <span data-ttu-id="75ee5-119">Assegnare il criterio della route vocale all'utente.</span><span class="sxs-lookup"><span data-stu-id="75ee5-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="75ee5-120">Creare una route vocale per un dispositivo analogico.</span><span class="sxs-lookup"><span data-stu-id="75ee5-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="75ee5-121">Per informazioni su come connettere un ATA a un SBC e configurare il SBC, vedere la guida alla configurazione del produttore SBC:</span><span class="sxs-lookup"><span data-stu-id="75ee5-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="75ee5-122">Documentazione di configurazione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="75ee5-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [<span data-ttu-id="75ee5-123">Documentazione di configurazione della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="75ee5-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="75ee5-124">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="75ee5-124">Step 1.</span></span>  <span data-ttu-id="75ee5-125">Connettere il SBC al routing diretto</span><span class="sxs-lookup"><span data-stu-id="75ee5-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="75ee5-126">Il comando seguente configura la connessione SBC come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="75ee5-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="75ee5-127">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="75ee5-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="75ee5-128">Porta di segnalazione 5068</span><span class="sxs-lookup"><span data-stu-id="75ee5-128">Signaling port 5068</span></span>
- <span data-ttu-id="75ee5-129">Modalità bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="75ee5-129">Media bypass mode</span></span>
- <span data-ttu-id="75ee5-130">Informazioni sulla cronologia delle chiamate inoltrate a SBC-</span><span class="sxs-lookup"><span data-stu-id="75ee5-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="75ee5-131">Intestazione P-Asserted-Identity (PAI) inoltrata insieme alla chiamata</span><span class="sxs-lookup"><span data-stu-id="75ee5-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="75ee5-132">Passaggio 2: creare l'utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="75ee5-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="75ee5-133">Il comando successivo crea un uso PSTN vuoto.</span><span class="sxs-lookup"><span data-stu-id="75ee5-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="75ee5-134">Gli usi PSTN online sono valori stringa usati per l'autorizzazione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="75ee5-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="75ee5-135">Un uso PSTN online collega un criterio vocale online a una route.</span><span class="sxs-lookup"><span data-stu-id="75ee5-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="75ee5-136">Questo esempio aggiunge la stringa "Interop" all'elenco corrente degli usi PSTN disponibili.</span><span class="sxs-lookup"><span data-stu-id="75ee5-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="75ee5-137">Passaggio 3: creare una route vocale e associarla all'utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="75ee5-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="75ee5-138">Questo comando crea una nuova route vocale online con l'identità "interoperabilità analogica" per l'intervallo di numeri + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="75ee5-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="75ee5-139">La route vocale è applicabile a un elenco di gateway online sbc.contoso.com e associa la route con l'utilizzo PSTN online "Interop".</span><span class="sxs-lookup"><span data-stu-id="75ee5-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="75ee5-140">Una route vocale include un'espressione regolare che identifica i numeri di telefono che verranno instradati tramite una determinata route vocale:</span><span class="sxs-lookup"><span data-stu-id="75ee5-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="75ee5-141">Passaggio 4: assegnare la route vocale all'utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="75ee5-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="75ee5-142">Questo comando crea un nuovo criterio di routing vocale per utente online con l'identità "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="75ee5-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="75ee5-143">A questo criterio viene assegnato un singolo utilizzo PSTN online: "Interop".</span><span class="sxs-lookup"><span data-stu-id="75ee5-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="75ee5-144">Passaggio 5: abilitare l'utente online</span><span class="sxs-lookup"><span data-stu-id="75ee5-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="75ee5-145">Questo comando consente di modificare l'account utente con Identity exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="75ee5-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="75ee5-146">In questo caso, l'account viene modificato per abilitare Enterprise Voice, l'implementazione Microsoft del VoIP, con la segreteria telefonica abilitata e assegna il numero + 14255000000 a questo utente.</span><span class="sxs-lookup"><span data-stu-id="75ee5-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="75ee5-147">Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant della società.</span><span class="sxs-lookup"><span data-stu-id="75ee5-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="75ee5-148">Passaggio 6: assegnare il criterio della route vocale a un utente</span><span class="sxs-lookup"><span data-stu-id="75ee5-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="75ee5-149">Questo comando assegna all'utente il criterio di routing vocale online per utente AnalogInteropPolicy con l'identità exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="75ee5-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="75ee5-150">Questo comando deve essere eseguito per ogni utente di Teams (esclusi gli utenti di dispositivi ATA) nel tenant della società.</span><span class="sxs-lookup"><span data-stu-id="75ee5-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="75ee5-151">Passaggio 7: creare una route vocale per un dispositivo analogico</span><span class="sxs-lookup"><span data-stu-id="75ee5-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="75ee5-152">Questo comando crea una route vocale online con Identity "Analog-Interop" per l'intervallo di numeri + 1425 4XX XX XX applicabile a un elenco di gateway online sbc.contoso.com e lo associa all'utilizzo PSTN online "Interop".</span><span class="sxs-lookup"><span data-stu-id="75ee5-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="75ee5-153">Questo comando deve essere eseguito per ogni dispositivo analogico con il modello di numero di telefono appropriato.</span><span class="sxs-lookup"><span data-stu-id="75ee5-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="75ee5-154">In alternativa, è possibile usare un modello di numero appropriato per i dispositivi analogici durante la configurazione della route vocale online durante uno dei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="75ee5-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="75ee5-155">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="75ee5-155">Considerations</span></span>

- <span data-ttu-id="75ee5-156">Se non diversamente specificato, un dispositivo analogico è un dispositivo che può inviare cifre DTMF per effettuare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="75ee5-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="75ee5-157">Ad esempio, telefoni analogici, fax e pagine generali.</span><span class="sxs-lookup"><span data-stu-id="75ee5-157">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="75ee5-158">I telefoni analogici collegati a un ATA non possono essere cercati da teams.</span><span class="sxs-lookup"><span data-stu-id="75ee5-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="75ee5-159">Gli utenti di teams devono immettere manualmente il numero di telefono associato al dispositivo per chiamare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75ee5-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="75ee5-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75ee5-160">See also</span></span>

[<span data-ttu-id="75ee5-161">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="75ee5-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="75ee5-162">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="75ee5-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
