---
title: Installare i file per Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Riepilogo: informazioni su come installare i file per Mediation Server in Skype for Business Server.'
ms.openlocfilehash: 4dc4c9971b74bf27d0f516ed70484646b666a845
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767119"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="f7dbf-103">Installare i file per Mediation Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7dbf-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f7dbf-104">**Riepilogo:** Informazioni su come installare i file per Mediation Server in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="f7dbf-105">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server, almeno come amministratore locale e un utente di dominio con appartenenza almeno al gruppo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="f7dbf-106">Usare la procedura descritta in questo argomento per eseguire la distribuzione guidata di Skype for Business Server per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server dopo avere usato generatore di topologie per definire e pubblicare il pool.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="f7dbf-107">Durante l'installazione di file Mediation Server è anche possibile installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7dbf-108">Questo argomento presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo nella topologia, come descritto in [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="f7dbf-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="f7dbf-109">Per installare i file per un pool di Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="f7dbf-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="f7dbf-110">Dal supporto di installazione fare clic con il pulsante destro del mouse su _ \<supporto\> _ per l'installazione **\setup\amd64\Setup.exe**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="f7dbf-111">Nella pagina **posizione di installazione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="f7dbf-112">Nella pagina **contratto di licenza con l'utente finale** fare clic su **Accetto**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="f7dbf-113">(Obbligatorio per continuare).</span><span class="sxs-lookup"><span data-stu-id="f7dbf-113">(Required to continue.)</span></span>
    
4. <span data-ttu-id="f7dbf-114">Nella pagina della **distribuzione guidata di Skype for Business Server** fare clic su **Installa o Aggiorna sistema di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="f7dbf-115">Accanto al **passaggio 1: installare l'archivio configurazione locale**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="f7dbf-116">Nella pagina **Configura replica locale della pagina Central Management store** accettare il recupero predefinito **direttamente dall'Central Management store**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f7dbf-117">Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="f7dbf-118">Accanto al **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Esegui**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="f7dbf-119">Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="f7dbf-120">Accanto al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="f7dbf-121">Seguire le istruzioni visualizzate per accettare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="f7dbf-122">Il Mediation Server richiede un certificato e quindi verrà eseguito due volte il **passaggio 3** : una volta per emettere il certificato richiesto e ancora una volta per assegnarlo.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="f7dbf-123">Quando il certificato è stato emesso e assegnato correttamente, accanto al **passaggio 4: avviare i servizi**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="f7dbf-124">Quando il **passaggio 4** è stato completato correttamente, riavviare il server e accedere al server come membro del gruppo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="f7dbf-125">Nel computer in cui è installato il pannello di controllo di Skype for Business Server verificare nella pagina **topologia** del pannello di controllo di Skype for Business Server che lo stato del servizio di Mediation Server sia visualizzato come segno di spunta verde.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="f7dbf-126">Se invece viene visualizzata una X rossa, selezionare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="f7dbf-127">Nel menu **azione** fare clic su **Avvia tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="f7dbf-128">Se sono stati aggiunti più computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="f7dbf-129">Se non è necessario installare file per Mediation Server per altri computer, seguire le procedure descritte in [configurare Trunks in Skype for Business Server](configure-trunks.md) per configurare le impostazioni per la connessione trunk tra questo pool di Mediation Server (o tutti i Mediation Server di un sito) e il relativo peer.</span><span class="sxs-lookup"><span data-stu-id="f7dbf-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

