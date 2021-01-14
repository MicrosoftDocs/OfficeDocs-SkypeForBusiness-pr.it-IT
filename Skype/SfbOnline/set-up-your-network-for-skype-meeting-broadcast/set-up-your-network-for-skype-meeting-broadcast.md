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
description: Informazioni sulla funzionalità Skype meeting broadcast di Skype for business online che consente di pianificare, produrre e trasmettere riunioni o eventi a un ampio pubblico online fino a 10.000 partecipanti.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865160"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="45ae9-103">Configurare la rete per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="45ae9-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="45ae9-104">Dopo aver [abilitato Skype meeting broadcast](enable-skype-meeting-broadcast.md) Skype meeting broadcast, è necessario configurare la rete.</span><span class="sxs-lookup"><span data-stu-id="45ae9-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="45ae9-105">Eseguire questa procedura se si vogliono tenere webinar e altre trasmissioni per gli utenti esterni all'azienda.</span><span class="sxs-lookup"><span data-stu-id="45ae9-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45ae9-106">Skype for business online si ritira il 31 luglio 2021, momento in cui l'accesso al servizio finirà.</span><span class="sxs-lookup"><span data-stu-id="45ae9-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="45ae9-107">Invitiamo i clienti a iniziare l'aggiornamento a Microsoft teams, il client principale per le comunicazioni e il lavoro di gruppo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45ae9-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="45ae9-108">Se non si ha esperienza con la configurazione del firewall, prendere in considerazione l'assunzione di un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="45ae9-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="45ae9-109">Per ignorare questo passaggio e aggiungere un altro business alla Federazione in modo da poterlo invitare alle trasmissioni, seguire i passaggi descritti in [consentire agli utenti di contattare utenti Skype for business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="45ae9-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="45ae9-110">Passaggio 1: configurare i domini consentiti</span><span class="sxs-lookup"><span data-stu-id="45ae9-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="45ae9-111">Usare **uno** dei metodi seguenti per configurare i domini consentiti:</span><span class="sxs-lookup"><span data-stu-id="45ae9-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="45ae9-112">**Metodo 1: usare l'interfaccia di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="45ae9-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="45ae9-113">Accedere all'interfaccia di amministrazione e quindi fare clic su componenti aggiuntivi servizi **Impostazioni** nella barra di spostamento sinistra  >  e quindi scegliere **Skype for business**.**&amp;**</span><span class="sxs-lookup"><span data-stu-id="45ae9-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="45ae9-114">Nella pagina **condivisione esterna** in **eccezioni di dominio** Selezionare **tutti i domini sono bloccati eccetto** e immettere i domini seguenti, separati da una virgola (,):</span><span class="sxs-lookup"><span data-stu-id="45ae9-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="45ae9-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="45ae9-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="45ae9-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="45ae9-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="45ae9-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="45ae9-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="45ae9-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="45ae9-118">resources.lync.com</span></span>

3. <span data-ttu-id="45ae9-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="45ae9-120">**Metodo 2: usare Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="45ae9-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="45ae9-121">Nel **menu Start** fare clic con il pulsante destro del mouse su **Windows PowerShell** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="45ae9-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="45ae9-122">Nella finestra di **Windows PowerShell** Digitare ogni riga e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="45ae9-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="45ae9-123">Passaggio 2: aggiungere domini, URL e indirizzi IP di Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="45ae9-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="45ae9-124">Il secondo passaggio del processo di configurazione è la prima volta che si aggiungono i domini necessari e quindi si aggiungono gli indirizzi IP e gli URL necessari per il funzionamento di Skype meeting broadcast.</span><span class="sxs-lookup"><span data-stu-id="45ae9-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="45ae9-125">**Aggiungere gli URL e gli indirizzi IP dell'endpoint Skype for business online necessari per vedere quali sono necessari** [qui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="45ae9-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="45ae9-126">Configurare Skype meeting broadcast in distribuzioni e organizzazioni ibride</span><span class="sxs-lookup"><span data-stu-id="45ae9-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="45ae9-127">Se si ha un'organizzazione di Skype for business online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e hanno utenti sia online che locali, è necessario eseguire altri passaggi di configurazione, oltre a quelli descritti sopra, per consentire all'organizzazione locale di comunicare con Skype for business online e consentire a tutti gli utenti di partecipare a una riunione Skype meeting broadcast.</span><span class="sxs-lookup"><span data-stu-id="45ae9-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="45ae9-128">Per vedere quali sono questi requisiti, vedere [configurare la distribuzione locale per Skype meeting broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="45ae9-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="45ae9-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="45ae9-129">Related topics</span></span>

[<span data-ttu-id="45ae9-130">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="45ae9-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="45ae9-131">URL e intervalli di indirizzi IP per Office 365</span><span class="sxs-lookup"><span data-stu-id="45ae9-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="45ae9-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="45ae9-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



