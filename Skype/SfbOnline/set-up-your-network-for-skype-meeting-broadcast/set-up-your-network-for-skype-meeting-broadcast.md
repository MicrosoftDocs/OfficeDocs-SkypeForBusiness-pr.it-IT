---
title: Configurare la rete per Skype Meeting Broadcast
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Informazioni sulla funzionalità Skype Meeting Broadcast di Skype for Business online che consente di pianificare, produrre e trasmettere riunioni o eventi a un pubblico online di grandi dimensioni fino a 10.000 partecipanti.
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106512"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="ff213-103">Configurare la rete per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="ff213-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="ff213-104">Dopo aver [abilitato Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, è necessario configurare la rete.</span><span class="sxs-lookup"><span data-stu-id="ff213-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="ff213-105">Eseguire questo passaggio se si vogliono tenere webinar e altre trasmissioni per utenti esterni all'azienda.</span><span class="sxs-lookup"><span data-stu-id="ff213-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff213-106">Skype for Business online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà.</span><span class="sxs-lookup"><span data-stu-id="ff213-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="ff213-107">Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff213-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="ff213-108">Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="ff213-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="ff213-109">Per ignorare questo passaggio e aggiungere un'altra attività alla federazione in modo da poterle invitare a trasmettere, seguire la procedura descritta in Consentire agli utenti di contattare utenti [esterni di Skype for Business.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="ff213-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="ff213-110">Passaggio 1: Configurare i domini consentiti</span><span class="sxs-lookup"><span data-stu-id="ff213-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="ff213-111">Usare **uno** dei metodi seguenti per configurare i domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="ff213-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="ff213-112">**Metodo 1: Usare l'interfaccia di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="ff213-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="ff213-113">Passare all'interfaccia di amministrazione e quindi nel riquadro di spostamento sinistro fare clic su Componenti aggiuntivi Servizi impostazioni e quindi scegliere Skype for  >  **&amp;** **Business.**</span><span class="sxs-lookup"><span data-stu-id="ff213-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="ff213-114">Nella pagina **Condivisione esterna** in **Eccezioni** dominio selezionare Tutti i domini sono bloccati tranne **e** immettere i domini seguenti, separati da una virgola (,):</span><span class="sxs-lookup"><span data-stu-id="ff213-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="ff213-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff213-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="ff213-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff213-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="ff213-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff213-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="ff213-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="ff213-118">resources.lync.com</span></span>

3. <span data-ttu-id="ff213-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ff213-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="ff213-120">**Metodo 2: Usare Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ff213-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="ff213-121">Nel **menu Start fare clic con** il pulsante destro **Windows PowerShell** clic su Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="ff213-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="ff213-122">Nella finestra **Windows PowerShell** digitare ogni riga e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="ff213-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="ff213-123">Passaggio 2: Aggiungere domini, URL e indirizzi IP Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="ff213-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="ff213-124">Il secondo passaggio del processo di configurazione consiste nell'aggiungere prima i domini necessari e quindi aggiungere gli indirizzi IP e gli URL necessari per il funzionamento di Skype Meeting Broadcast.</span><span class="sxs-lookup"><span data-stu-id="ff213-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="ff213-125">**Aggiungere gli URL degli endpoint e** gli indirizzi IP di Skype for Business Online necessari per vedere quali sono necessari [qui.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="ff213-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="ff213-126">Configurare Skype Meeting Broadcast nelle distribuzioni ibride e nelle organizzazioni</span><span class="sxs-lookup"><span data-stu-id="ff213-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="ff213-127">Se si ha un'organizzazione Skype for Business Online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e si hanno utenti sia online che locali, è necessario eseguire altre operazioni di configurazione oltre a quelle precedenti per consentire all'organizzazione locale di comunicare con Skype for Business Online e consentire a tutti gli utenti di partecipare a Skype Meeting Broadcast.</span><span class="sxs-lookup"><span data-stu-id="ff213-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="ff213-128">Per sapere quali sono questi requisiti, consulta Configurare la distribuzione [locale per Skype Meeting Broadcast.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="ff213-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff213-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ff213-129">Related topics</span></span>

[<span data-ttu-id="ff213-130">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="ff213-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="ff213-131">URL e intervalli di indirizzi IP per Office 365</span><span class="sxs-lookup"><span data-stu-id="ff213-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="ff213-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ff213-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)