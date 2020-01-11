---
title: Configurare l'integrazione tra Skype for Business Server e Outlook Web App locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Riepilogo: integrare Skype for Business Server e Outlook Web App.'
ms.openlocfilehash: 2aedd3b5e2399ae2487c0bb6da3e468d56567897
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002876"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="6402a-103">Configurare l'integrazione tra Skype for Business Server e Outlook Web App locale</span><span class="sxs-lookup"><span data-stu-id="6402a-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="6402a-104">**Riepilogo:** Integrare Skype for Business Server e Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="6402a-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="6402a-105">I clienti che usano distribuzioni locali Skype for Business Server possono configurare l'interoperabilità con Microsoft Outlook Web App in Microsoft Exchange online in modalità di distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="6402a-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="6402a-106">Le caratteristiche di interoperabilità includono il Single Sign-on e la messaggistica istantanea (IM) e l'integrazione della presenza con l'interfaccia di Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="6402a-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="6402a-107">Per abilitare questa integrazione, è necessario configurare l'Edge Server nella distribuzione di Skype for Business Server locale completando le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6402a-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="6402a-108">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="6402a-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="6402a-109">Configurare un provider di hosting nell'Edge Server</span><span class="sxs-lookup"><span data-stu-id="6402a-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="6402a-110">Verificare la replica dell'archivio di gestione centralizzato aggiornato</span><span class="sxs-lookup"><span data-stu-id="6402a-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="6402a-111">Configurare uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="6402a-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="6402a-112">Per integrare Skype for Business Server locale con Exchange Online, è necessario configurare uno spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="6402a-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="6402a-113">Lo stesso spazio per l'indirizzo del dominio SIP è supportato sia da Skype for Business Server che dal servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6402a-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="6402a-114">Usando Skype for Business Server Management Shell, configura il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** , usando i parametri visualizzati nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6402a-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="6402a-115">Il parametro **AllowFederatedUsers** specifica se gli utenti interni possono comunicare con utenti provenienti da domini federati.</span><span class="sxs-lookup"><span data-stu-id="6402a-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="6402a-116">Questa proprietà determina anche se gli utenti interni possono comunicare con gli utenti in uno scenario di spazio di indirizzi SIP condiviso con Skype for Business Server ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6402a-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="6402a-117">Per informazioni dettagliate sull'uso di Skype for Business Server Management Shell, vedere [Skype for Business Server Management Shell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6402a-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="6402a-118">Configurare un provider di hosting nell'Edge Server</span><span class="sxs-lookup"><span data-stu-id="6402a-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="6402a-119">Usando Skype for Business Server Management Shell, configura un provider di hosting nell'Edge Server eseguendo il cmdlet **New-CsHostingProvider** , usando i parametri nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6402a-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="6402a-120">Se si usa Office 365 gestito da 21Vianet in Cina, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per il servizio gestito da 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="6402a-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="6402a-121">Se si usa Office 365 GCC High, sostituire il valore per il parametro ProxyFqdn in questo esempio ("exap.um.outlook.com") con il nome di dominio completo per GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="6402a-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="6402a-122">**Identity** specifica un identificatore di valore di stringa univoco per il provider di hosting da creare, ad esempio "Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="6402a-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="6402a-123">I valori che contengono spazi devono essere racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="6402a-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="6402a-124">\*\*Enabled \*\* indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="6402a-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="6402a-125">Deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="6402a-125">This must be set to True.</span></span>

- <span data-ttu-id="6402a-126">**EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="6402a-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="6402a-127">Deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="6402a-127">This must be set to True.</span></span>

- <span data-ttu-id="6402a-128">**HostsOCSUsers** indica se il provider di hosting viene usato per ospitare Office Communications Server o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6402a-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="6402a-129">Deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="6402a-129">This must be set to False.</span></span>

- <span data-ttu-id="6402a-130">**ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="6402a-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="6402a-131">Per Exchange Online, il nome di dominio completo è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6402a-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="6402a-132">La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6402a-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="6402a-133">Deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="6402a-133">This must be set to False.</span></span>

- <span data-ttu-id="6402a-134">**VerificationLevel** Indica il livello di verifica consentito per i messaggi inviati da e verso il provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="6402a-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="6402a-135">Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="6402a-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="6402a-136">Se questo livello non è specificato, il messaggio verrà rifiutato come non verificabile.</span><span class="sxs-lookup"><span data-stu-id="6402a-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="6402a-137">Verificare la replica dell'archivio di gestione centralizzato aggiornato</span><span class="sxs-lookup"><span data-stu-id="6402a-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="6402a-138">Le modifiche apportate tramite i cmdlet nelle sezioni precedenti vengono applicate automaticamente all'Edge Server e in genere richiedono meno di un minuto per la replica.</span><span class="sxs-lookup"><span data-stu-id="6402a-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="6402a-139">È possibile convalidare lo stato della replica e verificare che le modifiche siano state applicate all'Edge Server usando i cmdlet seguenti.</span><span class="sxs-lookup"><span data-stu-id="6402a-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="6402a-140">Per verificare gli aggiornamenti della replica, in un server interno della distribuzione di Skype for Business Server, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="6402a-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="6402a-141">Controlla se il valore di UpToDate viene visualizzato TRUE per tutte le repliche.</span><span class="sxs-lookup"><span data-stu-id="6402a-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="6402a-142">Per verificare che le modifiche siano state applicate, nel server perimetrale eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="6402a-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="6402a-143">Verificare che le informazioni visualizzate corrispondano alle modifiche apportate nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6402a-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="6402a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6402a-144">See also</span></span>

[<span data-ttu-id="6402a-145">Fornire agli utenti di Skype for Business Server Voice mail nella messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="6402a-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="6402a-146">Integrazione della messaggistica unificata di Exchange ospitata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6402a-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
