---
title: La configurazione della rete per la trasmissione riunione Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Informazioni sulla funzionalità di trasmissione riunione Skype di Skype Business online che consente inoltre di pianificazione, prodotti e trasmissione riunioni o eventi ai gruppi di destinatari in linea di grandi dimensioni fino a 10.000 partecipanti."
ms.openlocfilehash: 3e4afb09d6a65654af418e14cc124e3c78dc0e0c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="025f9-103">La configurazione della rete per la trasmissione riunione Skype</span><span class="sxs-lookup"><span data-stu-id="025f9-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="025f9-104">Dopo aver [Abilitare trasmissione riunione Skype](enable-skype-meeting-broadcast.md) trasmissione riunione Skype, è necessario configurare la rete.</span><span class="sxs-lookup"><span data-stu-id="025f9-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="025f9-105">Eseguire questo passaggio se si desidera mantenere webinar e altre trasmissioni per gli utenti all'esterno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="025f9-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="025f9-106">Se non si è pratici di configurazione del firewall, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.</span><span class="sxs-lookup"><span data-stu-id="025f9-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="025f9-107">Per ignorare questo passaggio e aggiungere invece business diversa per la federazione in modo che possono essere invitati alle trasmissioni, seguire i passaggi descritti in [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="025f9-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="025f9-108">Passaggio 1: Impostare i domini consentiti</span><span class="sxs-lookup"><span data-stu-id="025f9-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="025f9-109">Per impostare i domini consentiti, utilizzare **uno** dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="025f9-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="025f9-110">**Metodo 1: Utilizzare l'interfaccia di amministrazione di Office 365**</span><span class="sxs-lookup"><span data-stu-id="025f9-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="025f9-111">Visitare il **Centro di amministrazione di Office 365** e quindi la barra di spostamento sinistra fare clic su **Impostazioni** > **servizi &amp; componenti aggiuntivi**e quindi fare clic su **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="025f9-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="025f9-112">Nella pagina **condivisione esterna** in **eccezioni di dominio**, selezionare **tutti i domini vengono bloccati, ad eccezione**e immettere i seguenti domini separati da una virgola (,):</span><span class="sxs-lookup"><span data-stu-id="025f9-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="025f9-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="025f9-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="025f9-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="025f9-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="025f9-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="025f9-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="025f9-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="025f9-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="025f9-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="025f9-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="025f9-118">**Metodo 2: Utilizzare Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="025f9-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="025f9-119">Dal **Menu Start di** **Windows PowerShell** pulsante destro del mouse e fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="025f9-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="025f9-120">Nella finestra di **Windows PowerShell** , digitare ogni riga e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="025f9-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="025f9-121">Passaggio 2: Aggiungere Skype riunione trasmissione domini, gli URL e IP indirizzi</span><span class="sxs-lookup"><span data-stu-id="025f9-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="025f9-122">Il secondo passaggio del processo di installazione è consente di aggiungere i domini necessarie e quindi aggiungono gli indirizzi IP e gli URL che sono necessari per trasmettere riunione Skype per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="025f9-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="025f9-123">**Aggiungere Skype necessarie per gli URL degli endpoint Business Online e gli indirizzi IP verificando quali sono necessari** [di seguito](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="025f9-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="025f9-124">Configurazione di trasmissione riunione Skype nelle organizzazioni e le distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="025f9-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="025f9-125">Se sono Skype per le organizzazioni aziendali in linea e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype per Business Server 2015 e avere agli utenti sia online e locale, sono disponibili altre operazioni di installazione è necessario eseguire Oltre a quelli sopra per abilitare l'organizzazione locale comunicare con Skype Business online e consentire a tutti gli utenti siano in grado di creare e partecipare a una riunione Skype trasmissione.</span><span class="sxs-lookup"><span data-stu-id="025f9-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="025f9-126">Per verificare quali sono i requisiti, vedere [configurare la distribuzione in locale per la trasmissione riunione Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="025f9-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="025f9-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="025f9-127">Related topics</span></span>

[<span data-ttu-id="025f9-128">Abilitare la trasmissione riunione Skype</span><span class="sxs-lookup"><span data-stu-id="025f9-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="025f9-129">URL e intervalli di indirizzi IP per Office 365</span><span class="sxs-lookup"><span data-stu-id="025f9-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="025f9-130">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="025f9-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

