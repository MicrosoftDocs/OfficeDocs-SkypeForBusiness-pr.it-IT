---
title: Abilitare il controllo delle chiamate remote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="4dd59-102">Abilitare il controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="4dd59-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dd59-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4dd59-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4dd59-104">Il controllo delle chiamate remote consente agli utenti di controllare i telefoni PBX (Private Branch Exchange) desktop tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dd59-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="4dd59-105">Se il controllo delle chiamate remote è stato distribuito nell'ambiente legacy e si vuole eseguire la migrazione di Lync Server 2013, è necessario svolgere le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dd59-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="4dd59-106">Installare un gateway SIP/CSTA e configurarlo per comunicare con il PBX.</span><span class="sxs-lookup"><span data-stu-id="4dd59-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="4dd59-107">È necessario eseguire questo passaggio quando si distribuisce il pool di piloti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dd59-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="4dd59-108">Dopo l'Unione della topologia e la migrazione dei criteri e delle impostazioni, configurare Lync Server 2013 per instradare le richieste CSTA al gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="4dd59-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="4dd59-109">Questo passaggio è un passaggio manuale che segue la migrazione automatica.</span><span class="sxs-lookup"><span data-stu-id="4dd59-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="4dd59-110">Per configurare il routing per le richieste CSTA, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dd59-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="4dd59-111">Rimuovere le voci di host autorizzati legacy (note come *voci del server attendibili* in Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="4dd59-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="4dd59-112">Se si esegue la migrazione di utenti dalla distribuzione legacy, assicurarsi di rimuovere tutte le voci di host autorizzati esistenti create per il gateway SIP/CSTA prima di configurare le nuove voci dell'applicazione attendibile nel pool di piloti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dd59-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="4dd59-113">Per informazioni dettagliate su come rimuovere le voci legacy dell'host autorizzato, vedere [rimuovere una voce ospitante autorizzata](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="4dd59-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="4dd59-114">Configurare una route statica per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="4dd59-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="4dd59-115">È possibile configurare una route statica per i singoli pool che si desidera supportare il controllo delle chiamate remote oppure una route statica globale in modo che ogni pool non configurato con una route statica a livello di pool usi la route statica globale.</span><span class="sxs-lookup"><span data-stu-id="4dd59-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="4dd59-116">Per informazioni dettagliate su come configurare la route statica, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4dd59-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4dd59-117">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in ogni pool per il quale si vuole supportare il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="4dd59-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="4dd59-118">Per informazioni dettagliate su come configurare una voce di applicazione attendibile, vedere [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4dd59-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="4dd59-119">Se è stato distribuito un gateway SIP/CSTA che usa TCP (Transmission Control Protocol) per connettersi a Lync Server 2013, definire l'indirizzo IP del gateway in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="4dd59-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="4dd59-120">Per informazioni dettagliate sulla definizione dell'indirizzo IP, vedere [definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4dd59-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="4dd59-121">Configurare gli utenti di Lync 2013 per il controllo delle chiamate remote abilitando il controllo delle chiamate remote e assegnando un URI (Uniform Resource Identifier) del server di linea e un URI di linea.</span><span class="sxs-lookup"><span data-stu-id="4dd59-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="4dd59-122">Quando si esegue la migrazione degli utenti dalla distribuzione legacy a Lync Server 2013, vengono migrate le impostazioni del controllo delle chiamate remote insieme alle altre impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="4dd59-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="4dd59-123">Se si personalizzano le regole di normalizzazione dei numeri di telefono della Rubrica nella distribuzione legacy, è necessario eseguire alcune attività manuali dopo il completamento della migrazione automatica di criteri e impostazioni per eseguire la migrazione delle regole di normalizzazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="4dd59-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="4dd59-124">Se non sono state personalizzate regole di normalizzazione, la Rubrica viene migrata insieme al resto della topologia.</span><span class="sxs-lookup"><span data-stu-id="4dd59-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="4dd59-125">Per informazioni dettagliate sulla migrazione manuale di regole di normalizzazione personalizzate, vedere [eseguire la migrazione della rubrica](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="4dd59-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

