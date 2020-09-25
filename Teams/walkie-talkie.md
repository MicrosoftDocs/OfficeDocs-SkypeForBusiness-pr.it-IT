---
title: Applicazione walkie-talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app walkie talkie in Microsoft teams, da una prospettiva ITAdmin.
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
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262503"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="49c63-103">App walkie talkie in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49c63-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="49c63-104">L'app walkie talkie in teams fornisce comunicazioni immediate push-to-Talk (PTT) per il team ed è ora disponibile in Android.</span><span class="sxs-lookup"><span data-stu-id="49c63-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="49c63-105">Walkie talkie consente agli utenti di connettersi con il proprio team usando gli stessi canali sottostanti di cui sono membri.</span><span class="sxs-lookup"><span data-stu-id="49c63-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="49c63-106">Solo gli utenti che si connettono a walkie talkie in un canale diventano partecipanti e possono comunicare tra loro tramite push-to-Talk, uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="49c63-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="49c63-107">Con walkie-talkie in teams, i lavoratori di i FIRSTLINE possono ora comunicare in modo sicuro con un'esperienza di PTT familiare senza dover trasportare radio ingombranti e il walkie-talkie funziona ovunque con WiFi o connettività Internet cellulare.</span><span class="sxs-lookup"><span data-stu-id="49c63-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="49c63-108">Introduzione</span><span class="sxs-lookup"><span data-stu-id="49c63-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="49c63-109">Distribuzione di walkie talkie</span><span class="sxs-lookup"><span data-stu-id="49c63-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="49c63-110">Attualmente, walkie talkie non è preinstallato.</span><span class="sxs-lookup"><span data-stu-id="49c63-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="49c63-111">Per abilitare questa funzionalità per gli utenti dell'organizzazione, è necessario aggiungere walkie talkie ai criteri di [configurazione dell'app](teams-app-setup-policies.md)   assegnati agli utenti dall'interfaccia di [amministrazione di teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="49c63-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="49c63-112">Una volta abilitato, walkie talkie sarà disponibile nell'app Android entro 48 ore.</span><span class="sxs-lookup"><span data-stu-id="49c63-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="49c63-113">Aggiunta di walkie talkie all'elenco delle app</span><span class="sxs-lookup"><span data-stu-id="49c63-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="49c63-114">Nell'interfaccia di amministrazione di Microsoft teams, in criteri di configurazione dell' **app teams**  >  **Setup policies**, è consigliabile consentire **il** **blocco degli utenti** impostato su attivato.</span><span class="sxs-lookup"><span data-stu-id="49c63-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="49c63-115">Quindi, nella sezione app appuntate, fare clic su **+ Aggiungi app**.</span><span class="sxs-lookup"><span data-stu-id="49c63-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

<span data-ttu-id="49c63-117">Nel riquadro **Aggiungi app Pinned** che viene visualizzato a destra usa la casella di testo **ricerca** per cercare walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="49c63-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="49c63-118">Quando si ha un risultato di ricerca, fare clic sul pulsante **Aggiungi** a destra del nome per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="49c63-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app Pinned con walkie immessa nel riquadro di ricerca e nell'app walkie talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

<span data-ttu-id="49c63-120">L'app walkie-talkie dovrebbe ora essere visualizzata nell'elenco delle app aggiunte ed essere disponibile per l'uso quando si fa clic sul pulsante **Salva** .</span><span class="sxs-lookup"><span data-stu-id="49c63-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco delle app bloccate con l'app walkie-talkie aggiunta e il pulsante Salva sotto l'elenco.":::

### <a name="network-documentation"></a><span data-ttu-id="49c63-122">Documentazione di rete</span><span class="sxs-lookup"><span data-stu-id="49c63-122">Network documentation</span></span>

<span data-ttu-id="49c63-123">Walkie talkie in teams richiede connettività Internet e al di sotto delle condizioni di rete necessarie per un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="49c63-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="49c63-124">Metrica</span><span class="sxs-lookup"><span data-stu-id="49c63-124">Metric</span></span> | <span data-ttu-id="49c63-125">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="49c63-125">Required</span></span> |
|---|---|
|<span data-ttu-id="49c63-126">Latenza (RTT)</span><span class="sxs-lookup"><span data-stu-id="49c63-126">Latency (RTT)</span></span> | <span data-ttu-id="49c63-127">< 300ms</span><span class="sxs-lookup"><span data-stu-id="49c63-127">< 300ms</span></span> |
|<span data-ttu-id="49c63-128">Jitter</span><span class="sxs-lookup"><span data-stu-id="49c63-128">Jitter</span></span> |<span data-ttu-id="49c63-129">< 30ms</span><span class="sxs-lookup"><span data-stu-id="49c63-129">< 30ms</span></span> |
|<span data-ttu-id="49c63-130">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="49c63-130">Packet Loss</span></span> |<span data-ttu-id="49c63-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="49c63-131">< 1%</span></span> |

<span data-ttu-id="49c63-132">Come indicato in precedenza, la qualità dei contenuti multimediali in tempo reale su una rete IP è fortemente influenzata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:</span><span class="sxs-lookup"><span data-stu-id="49c63-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="49c63-133">**Latenza** : è il tempo necessario per ottenere un pacchetto IP dal punto a al punto B della rete.</span><span class="sxs-lookup"><span data-stu-id="49c63-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="49c63-134">Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e la velocità della luce, incluso il sovraccarico aggiuntivo adottato dai vari router in mezzo.</span><span class="sxs-lookup"><span data-stu-id="49c63-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="49c63-135">La latenza viene misurata come RTT (Round Trip Time).</span><span class="sxs-lookup"><span data-stu-id="49c63-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="49c63-136">**Perdita di pacchetti** : spesso viene definita come percentuale di pacchetti persi in una determinata finestra di tempo.</span><span class="sxs-lookup"><span data-stu-id="49c63-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="49c63-137">La perdita di pacchetti influenza direttamente la qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto, alle perdite di burst di back-to-back che causano un cut-out audio completo.</span><span class="sxs-lookup"><span data-stu-id="49c63-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="49c63-138">**Jitter** : si tratta della variazione media di ritardo tra i pacchetti successivi.</span><span class="sxs-lookup"><span data-stu-id="49c63-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="49c63-139">L'utilizzo dei dati attesi da walkie talkie è di circa 20KB/s durante l'invio o la ricezione di audio.</span><span class="sxs-lookup"><span data-stu-id="49c63-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="49c63-140">Quando è inattivo, l'utilizzo previsto dei dati da walkie talkie è irrilevante.</span><span class="sxs-lookup"><span data-stu-id="49c63-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="49c63-141">Dispositivi walkie-talkie</span><span class="sxs-lookup"><span data-stu-id="49c63-141">Walkie Talkie devices</span></span>

<span data-ttu-id="49c63-142">I lavoratori I FIRSTLINE spesso devono parlare e ricevere chiamate walkie-talkie anche quando i loro telefoni sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="49c63-142">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="49c63-143">Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.</span><span class="sxs-lookup"><span data-stu-id="49c63-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="49c63-144">Cuffie</span><span class="sxs-lookup"><span data-stu-id="49c63-144">Headsets</span></span>
  - <span data-ttu-id="49c63-145">Auricolari cablati ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span><span class="sxs-lookup"><span data-stu-id="49c63-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="49c63-146">Auricolari wireless ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span><span class="sxs-lookup"><span data-stu-id="49c63-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="49c63-147">Telefoni robusti</span><span class="sxs-lookup"><span data-stu-id="49c63-147">Rugged phones</span></span>
  - <span data-ttu-id="49c63-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="49c63-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="49c63-149">[Altre info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="49c63-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="49c63-150">[Guida alla configurazione](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="49c63-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="49c63-151">Questi dispositivi non sono certificati in teams.</span><span class="sxs-lookup"><span data-stu-id="49c63-151">These devices are not Teams certified.</span></span> <span data-ttu-id="49c63-152">Sono stati convalidati per collaborare con walkie talkie teams.</span><span class="sxs-lookup"><span data-stu-id="49c63-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="49c63-153">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="49c63-153">License requirements</span></span>

<span data-ttu-id="49c63-154">L'app walkie talkie è inclusa in tutte le licenze a pagamento dei team in [abbonamenti a Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="49c63-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="49c63-155">Per altre informazioni su come ottenere teams, vedere [come si accede a Microsoft teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="49c63-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="49c63-156">Alcune funzionalità avanzate potrebbero richiedere licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="49c63-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="49c63-157">Ad esempio, l'integrazione con Samsung Galaxy XCover Pro richiede una licenza Knox.</span><span class="sxs-lookup"><span data-stu-id="49c63-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="49c63-158">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="49c63-158">Further information</span></span>

- <span data-ttu-id="49c63-159">ITAdmins può mantenere il controllo su chi usa walkie talkie attraverso i criteri per le app.</span><span class="sxs-lookup"><span data-stu-id="49c63-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="49c63-160">Se il lavoratore i FIRSTLINE usa dati mobili per comunicare tramite Team, walkie-talkie userà lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="49c63-160">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="49c63-161">Il walkie-talkie dovrebbe funzionare correttamente in situazioni di larghezza di banda ridotta o in situazioni in cui lo smartphone è connesso e funzionante.</span><span class="sxs-lookup"><span data-stu-id="49c63-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="49c63-162">Il walkie-talkie non funziona quando non c'è connettività.</span><span class="sxs-lookup"><span data-stu-id="49c63-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="49c63-163">Per altre informazioni sull'esperienza utente finale, vedere:</span><span class="sxs-lookup"><span data-stu-id="49c63-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="49c63-164">Guida introduttiva a teams walkie talkie</span><span class="sxs-lookup"><span data-stu-id="49c63-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="49c63-165">Comunicare con il team con il walkie-talkie</span><span class="sxs-lookup"><span data-stu-id="49c63-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
