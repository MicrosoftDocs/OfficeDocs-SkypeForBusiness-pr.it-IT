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
description: Leggere questo articolo per informazioni su come usare i dispositivi analogici con Telefono Microsoft system direct routing.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642096"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="a27ec-103">Come usare i dispositivi analogici con Sistema telefonico Direct Routing</span><span class="sxs-lookup"><span data-stu-id="a27ec-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="a27ec-104">Questo articolo descrive come usare i dispositivi analogici con Sistema telefonico routing diretto.</span><span class="sxs-lookup"><span data-stu-id="a27ec-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="a27ec-105">Per connettere dispositivi analogici a Routing diretto, è necessario usare un adattatore di telefonia analogica (ATA) e questo adattatore deve essere supportato dal fornitore SBC (Session Border Controller) certificato.</span><span class="sxs-lookup"><span data-stu-id="a27ec-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="a27ec-106">Quando un utente effettua una chiamata da un dispositivo analogico, la segnalazione e i supporti passano attraverso l'adattatore di telefonia analogica (ATA) fino a SBC.</span><span class="sxs-lookup"><span data-stu-id="a27ec-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="a27ec-107">Il servizio SBC invia la chiamata a un endpoint Microsoft Teams o alla rete PSTN (Public Switched Telephone Network) in base alla tabella di routing interna.</span><span class="sxs-lookup"><span data-stu-id="a27ec-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="a27ec-108">Quando un dispositivo effettua una chiamata, il percorso necessario dipende dai criteri di routing creati per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a27ec-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="a27ec-109">Nel diagramma seguente il routing diretto è configurato in modo che tutte le chiamate Teams da e verso i numeri compresi tra +1425 4XX XX XX e +1425 5XX XX XX prendano il percorso rosso (linea punteggiata) e qualsiasi chiamata PSTN da e verso numeri compresi tra +1425 4XX XX XX e qualsiasi altro numero ad eccezione dell'intervallo di numeri +1425 5XX XX XX deve assumere la linea blu (linea continua).</span><span class="sxs-lookup"><span data-stu-id="a27ec-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a27ec-110">![Diagramma che mostra la configurazione del routing diretto](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="a27ec-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="a27ec-111">Esempio: Come configurare l'uso di dispositivi analogici con Routing diretto</span><span class="sxs-lookup"><span data-stu-id="a27ec-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="a27ec-112">Per configurare l'uso di dispositivi analogici con Routing diretto, è necessario connettere l'adattatore di telefonia analogica all'SBC e configurare SBC in modo che funzioni con il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="a27ec-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="a27ec-113">Questo esempio illustra i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a27ec-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="a27ec-114">Connessione da SBC a Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="a27ec-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="a27ec-115">Creare l'utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="a27ec-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="a27ec-116">Creare una route vocale e associarla all'uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="a27ec-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="a27ec-117">Assegnare la route vocale all'uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="a27ec-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="a27ec-118">Abilitare l'utente online.</span><span class="sxs-lookup"><span data-stu-id="a27ec-118">Enable the online user.</span></span>
6. <span data-ttu-id="a27ec-119">Assegnare i criteri della route vocale all'utente.</span><span class="sxs-lookup"><span data-stu-id="a27ec-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="a27ec-120">Creare un percorso vocale per un dispositivo analogico.</span><span class="sxs-lookup"><span data-stu-id="a27ec-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="a27ec-121">Per informazioni su come connettere un ATA a un SBC e configurare SBC, vedere la guida alla configurazione del produttore SBC:</span><span class="sxs-lookup"><span data-stu-id="a27ec-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="a27ec-122">Documentazione sulla configurazione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a27ec-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="a27ec-123">Documentazione sulla configurazione della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="a27ec-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="a27ec-124">Documentazione sulla configurazione di Oracle</span><span class="sxs-lookup"><span data-stu-id="a27ec-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="a27ec-125">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="a27ec-125">Step 1.</span></span>  <span data-ttu-id="a27ec-126">Connessione da SBC a Routing diretto</span><span class="sxs-lookup"><span data-stu-id="a27ec-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="a27ec-127">Il comando seguente configura la connessione SBC nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a27ec-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="a27ec-128">Fqdn sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a27ec-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="a27ec-129">Porta di segnalazione 5068</span><span class="sxs-lookup"><span data-stu-id="a27ec-129">Signaling port 5068</span></span>
- <span data-ttu-id="a27ec-130">Modalità bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a27ec-130">Media bypass mode</span></span>
- <span data-ttu-id="a27ec-131">Informazioni sulla cronologia delle chiamate inoltrate all'SBC-</span><span class="sxs-lookup"><span data-stu-id="a27ec-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="a27ec-132">Intestazione P-Asserted-Identity (PAI) inoltrata insieme alla chiamata</span><span class="sxs-lookup"><span data-stu-id="a27ec-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="a27ec-133">Passaggio 2: Creare l'utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="a27ec-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="a27ec-134">Il comando successivo crea un utilizzo PSTN vuoto.</span><span class="sxs-lookup"><span data-stu-id="a27ec-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="a27ec-135">Gli utilizzi PSTN online sono valori stringa usati per l'autorizzazione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a27ec-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="a27ec-136">Un utilizzo PSTN online collega un criterio vocale online a una route.</span><span class="sxs-lookup"><span data-stu-id="a27ec-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="a27ec-137">Questo esempio aggiunge la stringa "Interop" all'elenco corrente degli utilizzi PSTN disponibili.</span><span class="sxs-lookup"><span data-stu-id="a27ec-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="a27ec-138">Passaggio 3: Creare una route vocale e associarla all'utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="a27ec-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="a27ec-139">Questo comando crea una nuova route vocale online con l'identità "analog-interop" per l'intervallo di numeri +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="a27ec-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="a27ec-140">La route vocale è applicabile a un elenco di gateway online sbc.contoso.com e associa la route all'uso pstn online "Interoperabilità".</span><span class="sxs-lookup"><span data-stu-id="a27ec-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="a27ec-141">Una route vocale include un'espressione regolare che identifica quali numeri di telefono verranno instradati attraverso una determinata route vocale:</span><span class="sxs-lookup"><span data-stu-id="a27ec-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="a27ec-142">Passaggio 4: Assegnare la route vocale all'utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="a27ec-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="a27ec-143">Questo comando crea un nuovo criterio di routing vocale online per utente con l'identità "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="a27ec-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="a27ec-144">A questo criterio viene assegnato un singolo utilizzo PSTN online: "Interoperabilità".</span><span class="sxs-lookup"><span data-stu-id="a27ec-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="a27ec-145">Passaggio 5: Abilitare l'utente online</span><span class="sxs-lookup"><span data-stu-id="a27ec-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="a27ec-146">Questo comando modifica l'account utente con l'exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a27ec-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="a27ec-147">In questo caso, l'account viene modificato per abilitare VoIP aziendale, l'implementazione Microsoft di VoIP, con la segreteria telefonica abilitata e assegna il numero +14255000000 a questo utente.</span><span class="sxs-lookup"><span data-stu-id="a27ec-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="a27ec-148">Questo comando deve essere eseguito per ogni Teams utente (esclusi gli utenti di dispositivi ATA) nel tenant aziendale.</span><span class="sxs-lookup"><span data-stu-id="a27ec-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="a27ec-149">Passaggio 6: Assegnare i criteri della route vocale a un utente</span><span class="sxs-lookup"><span data-stu-id="a27ec-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="a27ec-150">Questo comando assegna il criterio di routing vocale online per utente AnalogInteropPolicy all'utente con l'identità exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a27ec-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="a27ec-151">Questo comando deve essere eseguito per ogni Teams utente (esclusi gli utenti di dispositivi ATA) nel tenant aziendale.</span><span class="sxs-lookup"><span data-stu-id="a27ec-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="a27ec-152">Passaggio 7: Creare un percorso vocale per un dispositivo analogico</span><span class="sxs-lookup"><span data-stu-id="a27ec-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="a27ec-153">Questo comando crea una route vocale online con identità "analog-interop" per l'intervallo di numeri +1425 4XX XX XX applicabile a un elenco di gateway online sbc.contoso.com e la associa all'utilizzo pstn online "Interoperabilità".</span><span class="sxs-lookup"><span data-stu-id="a27ec-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="a27ec-154">Questo comando deve essere eseguito per ogni dispositivo analogico con un modello di numero di telefono appropriato.</span><span class="sxs-lookup"><span data-stu-id="a27ec-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="a27ec-155">In alternativa, è possibile usare un modello di numero appropriato per i dispositivi analogici durante la configurazione della route vocale online durante uno dei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="a27ec-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="a27ec-156">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="a27ec-156">Considerations</span></span>

- <span data-ttu-id="a27ec-157">Se non diversamente specificato, un dispositivo analogico è qualsiasi dispositivo in grado di inviare cifre DTMF per eseguire una chiamata.</span><span class="sxs-lookup"><span data-stu-id="a27ec-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="a27ec-158">Ad esempio, telefoni analogici, fax e pager in testa.</span><span class="sxs-lookup"><span data-stu-id="a27ec-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="a27ec-159">I telefoni analogici connessi a un ATA non possono essere cercati Teams.</span><span class="sxs-lookup"><span data-stu-id="a27ec-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="a27ec-160">Teams gli utenti devono immettere manualmente il numero di telefono associato al dispositivo per chiamare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a27ec-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="a27ec-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a27ec-161">See also</span></span>

[<span data-ttu-id="a27ec-162">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="a27ec-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="a27ec-163">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="a27ec-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
