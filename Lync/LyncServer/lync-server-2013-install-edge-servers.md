---
title: 'Lync Server 2013: installazione di server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="2019c-102">Installare server perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2019c-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2019c-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2019c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2019c-104">È possibile installare Lync Server 2013 nei server perimetrali utilizzando la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2019c-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="2019c-105">Eseguendo la distribuzione guidata in ogni server perimetrale, è possibile effettuare la maggior parte delle attività necessarie per installare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2019c-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="2019c-106">Per distribuire Lync Server 2013 in un server perimetrale, è necessario che sia già stato eseguito Generatore di topologie per definire e pubblicare la topologia del server perimetrale ed esportarla in un supporto disponibile dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2019c-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="2019c-107">Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) ed [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="2019c-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="2019c-108">Dopo aver utilizzato la distribuzione guidata per installare ogni server perimetrale, installare e assegnare i certificati necessari e avviare i servizi necessari, è possibile completare il programma di installazione utilizzando le informazioni riportate in [configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) per abilitare e configurare l'accesso degli utenti esterni e le informazioni di [Verifica della distribuzione di Edge in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) per convalidare l'installazione</span><span class="sxs-lookup"><span data-stu-id="2019c-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="2019c-109">Per installare un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="2019c-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="2019c-110">Eseguire l'accesso al computer in cui si desidera installare il server perimetrale come membri del gruppo Administrators locale o utilizzando un account con autorizzazioni e diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="2019c-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="2019c-111">Verificare che il file di configurazione della topologia creato utilizzando Generatore di topologie, quindi esportato e copiato su supporto esterno, sia disponibile nel server perimetrale, ad esempio accesso all'unità USB in cui è stato copiato il file di configurazione della topologia o verifica accesso alla condivisione di rete in cui è stato copiato il file.</span><span class="sxs-lookup"><span data-stu-id="2019c-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="2019c-112">Avviare la Distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="2019c-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2019c-p102">Se viene visualizzato un messaggio che indica la necessità di installare Microsoft Visual C++ Redistributable, fare clic su <STRONG>Sì</STRONG>. Nella finestra di dialogo successiva è possibile accettare il<STRONG> </STRONG>percorso di installazione predefinito oppure fare clic su <STRONG>Sfoglia</STRONG> per selezionare un percorso diverso e quindi fare clic su <STRONG>Installa</STRONG>. Nella finestra di dialogo successiva selezionare la casella di controllo <STRONG>Accetto i termini del Contratto di licenza</STRONG> e quindi fare clic su <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2019c-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="2019c-116">Nella Distribuzione guidata fare clic su **Installare o aggiornare il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2019c-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="2019c-117">Dopo che viene determinato lo stato della distribuzione, per **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2019c-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="2019c-118">Nella finestra di dialogo **Configura la replica locale dell'archivio di gestione centrale** fare clic su **Importa da un file (opzione consigliata per Edge Server)**, passare al percorso del file di configurazione della topologia esportato, selezionare il file con estensione zip, fare clic su **Apri** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2019c-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="2019c-119">Le informazioni di configurazione presenti nel file verranno lette e scritte nel file di configurazione XML nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2019c-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="2019c-120">Al termine del processo **Esecuzione comandi in corso**, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="2019c-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="2019c-121">Nella distribuzione guidata fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server** per installare i componenti perimetrali di lync Server 2013 specificati nel file di configurazione XML archiviato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2019c-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="2019c-122">Dopo aver completato l'installazione, utilizzare le informazioni contenute in [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) per installare e assegnare i certificati necessari prima di avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="2019c-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

