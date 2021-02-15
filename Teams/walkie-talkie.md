---
title: Applicazione Walkie Talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app Walkie-talkie in Microsoft Teams dal punto di vista DELL'ITAdmin.
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
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944591"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="eae03-103">Walkie Talkie app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eae03-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="eae03-104">L'app Walkie-talkie in Teams fornisce comunicazioni push-to-talk istantanee per il team ed è ora disponibile su Android.</span><span class="sxs-lookup"><span data-stu-id="eae03-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="eae03-105">Walkie Talkie consente agli utenti di connettersi con il proprio team utilizzando gli stessi canali sottostanti di cui sono membri.</span><span class="sxs-lookup"><span data-stu-id="eae03-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="eae03-106">Solo gli utenti che si connettono a Walkie Talkie in un canale diventano partecipanti e possono comunicare tra loro usando la funzionalità Push-to-talk, una alla volta.</span><span class="sxs-lookup"><span data-stu-id="eae03-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="eae03-107">Con Walkie Talkie in Teams, gli operatori in prima linea possono ora comunicare in modo sicuro con la nota esperienza PTT senza dover portare radio ingombrhe e Walkie Talkie funziona ovunque con WiFi o la connettività Internet cellulare.</span><span class="sxs-lookup"><span data-stu-id="eae03-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="eae03-108">Introduzione</span><span class="sxs-lookup"><span data-stu-id="eae03-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="eae03-109">Distribuzione di Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="eae03-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="eae03-110">Attualmente Walkie Talkie non è preinstallata.</span><span class="sxs-lookup"><span data-stu-id="eae03-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="eae03-111">Per abilitare questa funzionalità per gli utenti dell'organizzazione, è necessario aggiungere Walkie Talkie al criterio di configurazione [dell'app](teams-app-setup-policies.md)assegnato agli utenti   dall'interfaccia di amministrazione di [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="eae03-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="eae03-112">Una volta abilitata, Walkie Talkie sarà disponibile nell'app per Android entro 48 ore.</span><span class="sxs-lookup"><span data-stu-id="eae03-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="eae03-113">Aggiunta di Walkie Talkie all'elenco delle app</span><span class="sxs-lookup"><span data-stu-id="eae03-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="eae03-114">Nell'interfaccia di amministrazione di Microsoft Teams, in Criteri di **configurazione delle app di Teams,** l'opzione Consenti l'aggiunta di utenti dovrebbe essere  >  impostata su **On.** </span><span class="sxs-lookup"><span data-stu-id="eae03-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="eae03-115">Quindi, nella sezione App aggiunte, fare clic **su +Aggiungi app.**</span><span class="sxs-lookup"><span data-stu-id="eae03-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

<span data-ttu-id="eae03-117">Nel riquadro **Aggiungi app** aggiunte visualizzato a destra  usare la casella di testo Cerca per cercare Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="eae03-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="eae03-118">Quando è visualizzato come risultato della  ricerca, fare clic sul pulsante Aggiungi a destra del nome per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="eae03-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app aggiunte con Walkie immesso nel riquadro di ricerca e l'app Walkie Talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

<span data-ttu-id="eae03-120">L'app Walkie-talkie dovrebbe ora essere visualizzata nell'elenco app aggiunte ed essere disponibile per l'uso dopo aver fatto clic sul **pulsante** Salva.</span><span class="sxs-lookup"><span data-stu-id="eae03-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco delle app aggiunte con l'app Walkie Talkie aggiunta e il pulsante Salva sotto l'elenco.":::

### <a name="network-documentation"></a><span data-ttu-id="eae03-122">Documentazione di rete</span><span class="sxs-lookup"><span data-stu-id="eae03-122">Network documentation</span></span>

<span data-ttu-id="eae03-123">Walkie-talkie in Teams richiede la connettività Internet e al di sotto delle condizioni di rete sono necessarie per un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="eae03-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="eae03-124">Metrica</span><span class="sxs-lookup"><span data-stu-id="eae03-124">Metric</span></span> | <span data-ttu-id="eae03-125">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eae03-125">Required</span></span> |
|---|---|
|<span data-ttu-id="eae03-126">Latenza (RTT)</span><span class="sxs-lookup"><span data-stu-id="eae03-126">Latency (RTT)</span></span> | <span data-ttu-id="eae03-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="eae03-127">< 300ms</span></span> |
|<span data-ttu-id="eae03-128">Jitter</span><span class="sxs-lookup"><span data-stu-id="eae03-128">Jitter</span></span> |<span data-ttu-id="eae03-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="eae03-129">< 30ms</span></span> |
|<span data-ttu-id="eae03-130">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="eae03-130">Packet Loss</span></span> |<span data-ttu-id="eae03-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="eae03-131">< 1%</span></span> |

<span data-ttu-id="eae03-132">Come detto in precedenza, la qualità dei supporti multimediali in tempo reale su una rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma in particolare dalla quantità di:</span><span class="sxs-lookup"><span data-stu-id="eae03-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="eae03-133">**Latenza:** il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete.</span><span class="sxs-lookup"><span data-stu-id="eae03-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="eae03-134">Questo ritardo di propagazione in rete è strettamente collegato alla distanza fisica tra i due punti e alla velocità della luce, compreso un ulteriore sovraccarico dei vari router che si trova tra di loro.</span><span class="sxs-lookup"><span data-stu-id="eae03-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="eae03-135">La latenza viene misurata come tempo di round trip (RTT).</span><span class="sxs-lookup"><span data-stu-id="eae03-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="eae03-136">**Perdita pacchetti:** spesso viene definita come percentuale di pacchetti che vengono persi in un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="eae03-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="eae03-137">La perdita di pacchetti influisce direttamente sulla qualità audio, da pacchetti piccoli e singoli che non hanno quasi alcun impatto, a perdite di durata "back-to-back" che causano il cut-out completo dell'audio.</span><span class="sxs-lookup"><span data-stu-id="eae03-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="eae03-138">**Instabilità:** si tratta della variazione media del ritardo tra pacchetti successivi.</span><span class="sxs-lookup"><span data-stu-id="eae03-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="eae03-139">L'utilizzo dei dati previsto da Walkie Talkie è di circa 20 KB/s quando si invia o si riceve audio.</span><span class="sxs-lookup"><span data-stu-id="eae03-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="eae03-140">In caso di inattività, l'utilizzo previsto dei dati di Walkie Talkie è negligibile.</span><span class="sxs-lookup"><span data-stu-id="eae03-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="eae03-141">Dispositivi Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="eae03-141">Walkie Talkie devices</span></span>

<span data-ttu-id="eae03-142">Gli operatori in prima linea spesso devono parlare e ricevere chiamate Walkie Talkie anche quando i loro telefoni sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="eae03-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="eae03-143">Questa esperienza è possibile attraverso dispositivi specializzati con un pulsante PTT dedicato.</span><span class="sxs-lookup"><span data-stu-id="eae03-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="eae03-144">Cuffie</span><span class="sxs-lookup"><span data-stu-id="eae03-144">Headsets</span></span>
  - <span data-ttu-id="eae03-145">Cuffie con cavo[(Cuffie Elettronica)](https://www.kleinelectronics.com/poc-accessories/mtwt/)</span><span class="sxs-lookup"><span data-stu-id="eae03-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="eae03-146">Cuffie wireless[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="eae03-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="eae03-147">Telefoni frastagliati</span><span class="sxs-lookup"><span data-stu-id="eae03-147">Rugged phones</span></span>
  - <span data-ttu-id="eae03-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="eae03-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="eae03-149">[Altre info.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)</span><span class="sxs-lookup"><span data-stu-id="eae03-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="eae03-150">[Guida alla configurazione.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="eae03-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="eae03-151">Questi dispositivi non sono certificati teams.</span><span class="sxs-lookup"><span data-stu-id="eae03-151">These devices are not Teams certified.</span></span> <span data-ttu-id="eae03-152">Sono stati convalidati per funzionare con Teams Walkie Talkie.</span><span class="sxs-lookup"><span data-stu-id="eae03-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="eae03-153">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="eae03-153">License requirements</span></span>

<span data-ttu-id="eae03-154">L'app Walkie Talkie è inclusa in tutte le licenze a pagamento di Teams [negli abbonamenti a Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)</span><span class="sxs-lookup"><span data-stu-id="eae03-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="eae03-155">Per altre informazioni su come ottenere Teams, vedere [Come si accede a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="eae03-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="eae03-156">Alcune caratteristiche avanzate possono richiedere licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="eae03-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="eae03-157">Ad esempio, l'integrazione con Samsung Galaxy XCover Pro richiede una licenza Knox.</span><span class="sxs-lookup"><span data-stu-id="eae03-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="eae03-158">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="eae03-158">Further information</span></span>

- <span data-ttu-id="eae03-159">Gli ITAdmin possono mantenere il controllo su chi usa Walkie Talkie tramite i criteri app.</span><span class="sxs-lookup"><span data-stu-id="eae03-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="eae03-160">Se il tuo frontline usa i dati mobili per comunicare tramite Teams, Walkie Talkie userà lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="eae03-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="eae03-161">Walkie Talkie dovrebbe funzionare bene in situazioni con larghezza di banda ridotta o in situazioni in cui lo smartphone è connesso e funzionante.</span><span class="sxs-lookup"><span data-stu-id="eae03-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="eae03-162">Walkie Talkie non funzionerà se non c'è connettività.</span><span class="sxs-lookup"><span data-stu-id="eae03-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="eae03-163">Per ulteriori informazioni sull'esperienza utente finale, vedere:</span><span class="sxs-lookup"><span data-stu-id="eae03-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="eae03-164">Introduzione a Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="eae03-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="eae03-165">Comunicare con il team con Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="eae03-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
