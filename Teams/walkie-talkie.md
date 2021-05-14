---
title: Applicazione Walkie Talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app Walkie Talkie in Microsoft Teams, dal punto di vista dell'ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479073"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="1ffab-103">App Walkie Talkie in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ffab-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="1ffab-104">L'app Walkie Talkie in Teams fornisce comunicazioni push-to-talk istantanee (PTT) per il team ed è ora disponibile su Android.</span><span class="sxs-lookup"><span data-stu-id="1ffab-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="1ffab-105">Walkie Talkie consente agli utenti di connettersi con il team usando gli stessi canali sottostanti di cui sono membri.</span><span class="sxs-lookup"><span data-stu-id="1ffab-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="1ffab-106">Solo gli utenti che si connettono a Walkie Talkie in un canale diventano partecipanti e possono comunicare tra loro usando push-to-talk, uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="1ffab-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="1ffab-107">Con Walkie Talkie in Teams, i lavoratori frontline ora possono comunicare in modo sicuro con un'esperienza PTT familiare senza dover portare radio ingombrante, e Walkie Talkie funziona ovunque con connessione WiFi o rete cellulare Internet.</span><span class="sxs-lookup"><span data-stu-id="1ffab-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="1ffab-108">Introduzione</span><span class="sxs-lookup"><span data-stu-id="1ffab-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="1ffab-109">Distribuzione di Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="1ffab-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="1ffab-110">Attualmente, Walkie Talkie è disponibile per i dispositivi Android con Google Servizi mobili (GMS) e non è preinstallato.</span><span class="sxs-lookup"><span data-stu-id="1ffab-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="1ffab-111">Per abilitare questa funzionalità per gli utenti dell'organizzazione, è necessario aggiungere Walkie Talkie ai criteri di configurazione delle [app](teams-app-setup-policies.md)assegnati agli utenti dall'interfaccia di amministrazione   di [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1ffab-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="1ffab-112">Una volta abilitata, Walkie Talkie sarà disponibile nell'app Android entro 48 ore.</span><span class="sxs-lookup"><span data-stu-id="1ffab-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="1ffab-113">Aggiunta di Walkie Talkie all'elenco delle app</span><span class="sxs-lookup"><span data-stu-id="1ffab-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="1ffab-114">Nell'Microsoft Teams di amministrazione, in Teams criteri di configurazione **dell'app,** l'opzione Consenti blocco utente dovrebbe essere  >  impostata su  **Su**.</span><span class="sxs-lookup"><span data-stu-id="1ffab-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="1ffab-115">Quindi, nella sezione App aggiunte fare clic su **+Aggiungi app.**</span><span class="sxs-lookup"><span data-stu-id="1ffab-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

<span data-ttu-id="1ffab-117">Nel riquadro **Aggiungi app** aggiunte visualizzato a destra  usare la casella di testo Cerca per cercare Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="1ffab-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="1ffab-118">Una volta visualizzato come risultato della ricerca, selezionare il **pulsante Aggiungi** a destra del nome per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="1ffab-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app aggiunte con Walkie immesso nel riquadro di ricerca e l'app Walkie Talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

<span data-ttu-id="1ffab-120">L'app Walkie Talkie dovrebbe ora essere visualizzata nell'elenco App aggiunte ed essere disponibile per l'uso dopo aver fatto clic sul **pulsante** Salva.</span><span class="sxs-lookup"><span data-stu-id="1ffab-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco delle app aggiunte con l'app Walkie Talkie aggiunta e il pulsante Salva sotto l'elenco.":::

### <a name="network-documentation"></a><span data-ttu-id="1ffab-122">Documentazione di rete</span><span class="sxs-lookup"><span data-stu-id="1ffab-122">Network documentation</span></span>

<span data-ttu-id="1ffab-123">Walkie Talkie in Teams la connettività Internet e al di sotto delle condizioni di rete sono necessarie per un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="1ffab-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="1ffab-124">Metrica</span><span class="sxs-lookup"><span data-stu-id="1ffab-124">Metric</span></span> | <span data-ttu-id="1ffab-125">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1ffab-125">Required</span></span> |
|---|---|
|<span data-ttu-id="1ffab-126">Latenza (RTT)</span><span class="sxs-lookup"><span data-stu-id="1ffab-126">Latency (RTT)</span></span> | <span data-ttu-id="1ffab-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="1ffab-127">< 300ms</span></span> |
|<span data-ttu-id="1ffab-128">Jitter</span><span class="sxs-lookup"><span data-stu-id="1ffab-128">Jitter</span></span> |<span data-ttu-id="1ffab-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="1ffab-129">< 30ms</span></span> |
|<span data-ttu-id="1ffab-130">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="1ffab-130">Packet Loss</span></span> |<span data-ttu-id="1ffab-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="1ffab-131">< 1%</span></span> |

<span data-ttu-id="1ffab-132">Come indicato in precedenza, la qualità dei supporti multimediali in tempo reale su una rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma in particolare dalla quantità di:</span><span class="sxs-lookup"><span data-stu-id="1ffab-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="1ffab-133">**Latenza:** il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete.</span><span class="sxs-lookup"><span data-stu-id="1ffab-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="1ffab-134">Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e alla velocità della luce, incluso il sovraccarico dei vari router in mezzo.</span><span class="sxs-lookup"><span data-stu-id="1ffab-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="1ffab-135">La latenza viene misurata come tempo di round trip (RTT).</span><span class="sxs-lookup"><span data-stu-id="1ffab-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="1ffab-136">**Instabilità tra gli arrivi:** questa è la variazione media del ritardo tra pacchetti successivi.</span><span class="sxs-lookup"><span data-stu-id="1ffab-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="1ffab-137">**Perdita di pacchetti:** spesso viene definita come percentuale di pacchetti persi in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="1ffab-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="1ffab-138">La perdita di pacchetti influisce direttamente sulla qualità audio, da piccoli pacchetti persi individuali che non hanno quasi alcun impatto, a perdite di burst back-to-back che causano il cut-out audio completo.</span><span class="sxs-lookup"><span data-stu-id="1ffab-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="1ffab-139">L'utilizzo previsto dei dati da Walkie Talkie è di circa 20 Kb/s quando si invia o si riceve l'audio.</span><span class="sxs-lookup"><span data-stu-id="1ffab-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="1ffab-140">Quando si è inattivi, l'utilizzo previsto dei dati da Walkie Talkie è trascurabile.</span><span class="sxs-lookup"><span data-stu-id="1ffab-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="1ffab-141">Dispositivi Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="1ffab-141">Walkie Talkie devices</span></span>

<span data-ttu-id="1ffab-142">I lavoratori in prima linea spesso devono parlare e ricevere chiamate Walkie Talkie anche quando i loro telefoni sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="1ffab-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="1ffab-143">Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.</span><span class="sxs-lookup"><span data-stu-id="1ffab-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="1ffab-144">**Cuffie**</span><span class="sxs-lookup"><span data-stu-id="1ffab-144">**Headsets**</span></span>
  - <span data-ttu-id="1ffab-145">Cuffie wireless</span><span class="sxs-lookup"><span data-stu-id="1ffab-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="1ffab-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="1ffab-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="1ffab-147">Cuffie cablate</span><span class="sxs-lookup"><span data-stu-id="1ffab-147">Wired headsets</span></span> 
    - [<span data-ttu-id="1ffab-148">Klein Electronics</span><span class="sxs-lookup"><span data-stu-id="1ffab-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="1ffab-149">**Telefoni robusti**</span><span class="sxs-lookup"><span data-stu-id="1ffab-149">**Rugged phones**</span></span>
  - <span data-ttu-id="1ffab-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), Galaxy [XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="1ffab-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="1ffab-151">Configurazione manuale: con Teams installato, passare Impostazioni > funzionalità avanzate > XCover/Active key.</span><span class="sxs-lookup"><span data-stu-id="1ffab-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="1ffab-152">Attivare "Ctrl XCover key with app" e selezionare "Teams"</span><span class="sxs-lookup"><span data-stu-id="1ffab-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="1ffab-153">Configurazione MDM</span><span class="sxs-lookup"><span data-stu-id="1ffab-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="1ffab-154">Questi dispositivi non sono Teams certificati.</span><span class="sxs-lookup"><span data-stu-id="1ffab-154">These devices are not Teams certified.</span></span> <span data-ttu-id="1ffab-155">Sono stati convalidati per funzionare con Teams Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="1ffab-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="1ffab-156">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="1ffab-156">License requirements</span></span>

<span data-ttu-id="1ffab-157">L'app Walkie Talkie è inclusa in tutte le licenze a pagamento Teams in [Office 365 abbonamenti.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="1ffab-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="1ffab-158">Per altre informazioni su come ottenere Teams, vedere [Come si ottiene l'accesso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="1ffab-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="1ffab-159">Alcune funzionalità avanzate possono richiedere licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1ffab-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="1ffab-160">Ad esempio, l'integrazione con Samsung Galaxy XCover Pro richiede una licenza Knox.</span><span class="sxs-lookup"><span data-stu-id="1ffab-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="1ffab-161">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="1ffab-161">Further information</span></span>

- <span data-ttu-id="1ffab-162">Gli amministratori IT possono mantenere il controllo su chi usa Walkie Talkie tramite i criteri delle app.</span><span class="sxs-lookup"><span data-stu-id="1ffab-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="1ffab-163">Se il worker frontline usa i dati mobili per comunicare tramite Teams, Walkie Talkie userà lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="1ffab-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="1ffab-164">Walkie Talkie dovrebbe funzionare bene in situazioni con larghezza di banda ridotta o in situazioni in cui lo smartphone è connesso e funzionante.</span><span class="sxs-lookup"><span data-stu-id="1ffab-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="1ffab-165">Walkie Talkie non funzionerà quando non c'è connettività.</span><span class="sxs-lookup"><span data-stu-id="1ffab-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="1ffab-166">Per altre informazioni sull'esperienza utente finale, vedere:</span><span class="sxs-lookup"><span data-stu-id="1ffab-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="1ffab-167">Introduzione a Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="1ffab-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="1ffab-168">Comunicare con il team con Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="1ffab-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
