---
title: 'Lync Server 2013: Installare server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211baa13f80e89fa081b6bf65d4bd7e90d50d000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="0d57a-102">Installare server perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d57a-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d57a-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0d57a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0d57a-104">Si installa Lync Server 2013 in Edge Server tramite la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d57a-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="0d57a-105">Eseguendo la distribuzione guidata in ogni Edge Server, è possibile completare la maggior parte delle attività necessarie per configurare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0d57a-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="0d57a-106">Per distribuire Lync Server 2013 in un server perimetrale, è necessario avere già eseguito Generatore di topologia per definire e pubblicare la topologia di Edge Server ed esportarla in elementi multimediali disponibili nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0d57a-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="0d57a-107">Per informazioni dettagliate, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) ed [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="0d57a-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="0d57a-108">Dopo aver usato la distribuzione guidata per installare ogni Edge Server, installare e assegnare i certificati necessari e avviare i servizi necessari, è possibile completare la configurazione usando le informazioni in [configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) per abilitare e configurare l'accesso degli utenti esterni e le informazioni per [verificare la distribuzione di Edge in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) per convalidare la configurazione, inclusa la connettività del server</span><span class="sxs-lookup"><span data-stu-id="0d57a-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="0d57a-109">Per installare un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="0d57a-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="0d57a-110">Accedere al computer in cui si vuole installare l'Edge Server come membro del gruppo Administrators locale o un account con autorizzazioni e diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="0d57a-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="0d57a-111">Verificare che il file di configurazione della topologia creato con generatore di topologie e quindi esportato e copiato in elementi multimediali esterni sia disponibile nell'Edge Server, ad esempio accesso all'unità USB in cui è stato copiato il file di configurazione della topologia o verifica accesso alla condivisione di rete in cui è stato copiato il file.</span><span class="sxs-lookup"><span data-stu-id="0d57a-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="0d57a-112">Avviare la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="0d57a-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d57a-113">Se viene visualizzato un messaggio che informa che è necessario installare Microsoft Visual C++ ridistribuibile, fare clic su <STRONG>Sì</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0d57a-113">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>.</span></span> <span data-ttu-id="0d57a-114">Nella finestra di dialogo successiva è possibile accettare il percorso di <STRONG>installazione</STRONG> predefinito oppure fare clic sul pulsante <STRONG>Sfoglia</STRONG> per selezionare un percorso alternativo e quindi fare clic su <STRONG>Installa</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0d57a-114">In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>.</span></span> <span data-ttu-id="0d57a-115">Nella finestra di dialogo successiva selezionare la casella <STRONG>di controllo Accetto i termini del contratto di licenza</STRONG> e quindi fare clic su <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0d57a-115">In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="0d57a-116">Nella distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.</span><span class="sxs-lookup"><span data-stu-id="0d57a-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="0d57a-117">Dopo che la procedura guidata determina lo stato di distribuzione, al **passaggio 1. Installare l'archivio di configurazione locale**, fare clic su **Esegui** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d57a-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="0d57a-118">Nella finestra di dialogo **Configura replica locale di Central Management store** fare clic su **Importa da un file (consigliato per Edge Server)**, spostarsi nel percorso del file di configurazione della topologia esportata, selezionare il file con estensione zip, fare clic su **Apri**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d57a-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="0d57a-119">La distribuzione guidata legge le informazioni di configurazione dal file di configurazione e scrive il file di configurazione XML nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="0d57a-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="0d57a-120">Dopo aver completato il processo di **esecuzione dei comandi** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="0d57a-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="0d57a-121">Nella distribuzione guidata fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i componenti Edge di lync Server 2013 specificati nel file di configurazione XML archiviato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="0d57a-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="0d57a-122">Dopo aver completato l'installazione, usare le informazioni in [configurare i certificati di Edge per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) per installare e assegnare i certificati necessari prima di avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="0d57a-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

