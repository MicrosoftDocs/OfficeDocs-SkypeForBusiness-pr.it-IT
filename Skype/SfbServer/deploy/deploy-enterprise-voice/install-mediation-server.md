---
title: Installare i file per Mediation Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830796"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="987a3-103">Installare i file per Mediation Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="987a3-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="987a3-104">**Riepilogo:** Informazioni su come installare i file per Mediation Server in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="987a3-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="987a3-105">Per eseguire questa procedura, è necessario accedere al server almeno come amministratore locale e come utente di dominio appartenente almeno al gruppo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="987a3-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="987a3-106">Utilizzare la procedura descritta in questo argomento per eseguire la distribuzione guidata di Skype for Business Server per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server dopo aver utilizzato il generatore di topologie per definire e pubblicare il pool.</span><span class="sxs-lookup"><span data-stu-id="987a3-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="987a3-107">Quando si installano i file Mediation Server, è inoltre necessario installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="987a3-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="987a3-108">In questo argomento si presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo nella topologia, come descritto in [deploy a Mediation Server in Generatore di topologie in Skype for Business Server](deploy-a-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="987a3-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="987a3-109">Per installare i file per un pool Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="987a3-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="987a3-110">Dal supporto di installazione fare clic con il pulsante destro del mouse su  _\<installation media\>_ **\Setup\amd64\Setup.exe** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="987a3-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="987a3-111">Nella pagina **Percorso di installazione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="987a3-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="987a3-p102">Nella pagina **Contratto di licenza con l'utente finale** fare clic su **Accetto** e quindi su **OK**. Questa operazione è obbligatoria per proseguire.</span><span class="sxs-lookup"><span data-stu-id="987a3-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="987a3-114">Nella pagina **distribuzione guidata di Skype for Business Server** , fare clic su **Installa o aggiorna il sistema di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="987a3-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="987a3-115">Accanto a **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="987a3-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="987a3-116">Nella pagina **Configura la replica locale dell'archivio di gestione centrale** accettare l'impostazione predefinita **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="987a3-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="987a3-117">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="987a3-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="987a3-118">Accanto a **passaggio 2: installazione o rimozione componenti di Skype for Business Server**, fare clic su **Esegui**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="987a3-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="987a3-119">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="987a3-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="987a3-p103">Accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**. Seguire le istruzioni visualizzate sullo schermo, accettando le impostazioni predefinite. Il Mediation Server richiede un certificato, quindi il **Passaggio 3** verrà eseguito due volte, una per emettere il certificato necessario e l'altra per assegnarlo.</span><span class="sxs-lookup"><span data-stu-id="987a3-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="987a3-123">Dopo che il certificato è stato emesso e assegnato correttamente, accanto **Passaggio 4: Avvia servizi** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="987a3-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="987a3-124">Al termine del **Passaggio 4**, riavviare il server e accedere come membro del gruppo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="987a3-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="987a3-125">Nel computer in cui è in esecuzione il pannello di controllo di Skype for Business Server, verificare nella pagina **topologia** del pannello di controllo di Skype for Business Server che lo stato del servizio del Mediation Server sia visualizzato come segno di spunta verde.</span><span class="sxs-lookup"><span data-stu-id="987a3-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="987a3-126">Se invece appare una X rossa, selezionare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="987a3-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="987a3-127">Scegliere **Avvia tutti i servizi** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="987a3-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="987a3-128">Se è stato aggiunto più di un computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="987a3-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="987a3-129">Se non è necessario installare i file per Mediation Server per altri computer, seguire le procedure riportate in [Configure Trunks in Skype for Business Server](configure-trunks.md) per configurare le impostazioni per la connessione trunk tra il pool di Mediation Server (o tutti i Mediation Server in un sito) e il relativo peer.</span><span class="sxs-lookup"><span data-stu-id="987a3-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

