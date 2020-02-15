---
title: Abilitare il controllo delle chiamate remote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e7e6fef4b882a7358a49a994c10829ad5c8a257
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="ef277-102">Abilitare il controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="ef277-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef277-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ef277-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ef277-104">Il controllo delle chiamate remote consente agli utenti di controllare i propri telefoni PBX (Private Branch Exchange) tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef277-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="ef277-105">Se è stato distribuito il controllo delle chiamate remote nell'ambiente legacy e si desidera eseguire la migrazione di Lync Server 2013, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef277-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="ef277-106">Installare un gateway SIP/CSTA e configurarlo per la comunicazione con il PBX.</span><span class="sxs-lookup"><span data-stu-id="ef277-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="ef277-107">È necessario eseguire questo passaggio quando si distribuisce il pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef277-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="ef277-108">Dopo aver unito la topologia e aver eseguito la migrazione dei criteri e delle impostazioni, configurare Lync Server 2013 per instradare le richieste CSTA al gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="ef277-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="ef277-109">Questo passaggio deve essere eseguito manualmente dopo la migrazione automatizzata.</span><span class="sxs-lookup"><span data-stu-id="ef277-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="ef277-110">Per configurare il routing per le richieste CSTA, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef277-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="ef277-111">Rimuovere le voci host autorizzate legacy (note come *voci del server attendibili* in Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="ef277-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="ef277-112">Se si esegue la migrazione degli utenti dalla distribuzione legacy, assicurarsi di rimuovere tutte le voci host autorizzate esistenti create per il gateway SIP/CSTA prima di configurare nuove voci dell'applicazione attendibili nel pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef277-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="ef277-113">Per informazioni dettagliate sulla rimozione delle voci host autorizzate legacy, vedere [Remove an Authorized host entry](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="ef277-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="ef277-114">Configurare una route statica per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="ef277-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="ef277-115">È possibile configurare una route statica per i singoli pool che si desidera supportino il controllo delle chiamate remote oppure una route statica globale in modo che ogni pool non configurato con una route statica a livello di pool utilizzi la route statica globale.</span><span class="sxs-lookup"><span data-stu-id="ef277-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="ef277-116">Per informazioni dettagliate su come configurare la route statica, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef277-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ef277-117">Configurare una voce applicazione attendibile per il controllo delle chiamate remote in ogni pool per il quale si desidera il supporto per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="ef277-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="ef277-118">Per informazioni dettagliate sulla configurazione di una voce di applicazione attendibile, vedere [Configure a Trusted Application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef277-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="ef277-119">Se è stato distribuito un gateway SIP/CSTA che utilizza il protocollo TCP (Transmission Control Protocol) per la connessione a Lync Server 2013, definire l'indirizzo IP del gateway in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ef277-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="ef277-120">Per informazioni dettagliate sulla definizione dell'indirizzo IP, vedere [define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ef277-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="ef277-121">Configurare gli utenti di Lync 2013 per il controllo delle chiamate remote abilitando il controllo delle chiamate remote e assegnando un URI (Uniform Resource Identifier) del server di linea e un URI di linea.</span><span class="sxs-lookup"><span data-stu-id="ef277-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="ef277-122">Quando si esegue la migrazione degli utenti dalla distribuzione legacy a Lync Server 2013, le impostazioni del controllo delle chiamate remote vengono migrate insieme alle altre impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="ef277-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="ef277-123">Se nella distribuzione legacy sono state personalizzate le regole di normalizzazione dei numeri di telefono della Rubrica, è necessario eseguire alcune attività manuali al termine della migrazione automatizzata di criteri e impostazioni per eseguire la migrazione delle regole di normalizzazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ef277-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="ef277-124">Se tali regole non sono state personalizzate, la migrazione della Rubrica viene eseguita insieme al resto della topologia.</span><span class="sxs-lookup"><span data-stu-id="ef277-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="ef277-125">Per informazioni dettagliate sulla migrazione manuale delle regole di normalizzazione personalizzate, vedere [Migrate Address Book](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="ef277-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

