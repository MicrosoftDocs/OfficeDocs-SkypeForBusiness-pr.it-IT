---
title: 'Lync Server 2013: configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520463"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="09e76-102">Configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e76-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e76-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="09e76-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="09e76-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la sezione **configurazione di Persistent Chat** della pagina **chat** persistente per configurare le impostazioni di chat persistente a livello globale in cui si applica a tutti i pool di server Chat persistente o per un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="09e76-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09e76-105">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="09e76-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="09e76-106">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09e76-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="09e76-107">Per configurare le opzioni di chat persistente a livello globale</span><span class="sxs-lookup"><span data-stu-id="09e76-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="09e76-108">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="09e76-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09e76-109">Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="09e76-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="09e76-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09e76-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="09e76-111">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09e76-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="09e76-112">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09e76-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="09e76-113">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="09e76-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="09e76-114">Nella pagina **Configurazione Persistent Chat** fare clic su **nuovo** e quindi su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="09e76-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="09e76-115">Scegliere questa opzione se si desidera che la configurazione venga applicata a tutti i pool di server Chat persistente distribuiti nel sito.</span><span class="sxs-lookup"><span data-stu-id="09e76-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="09e76-116">Fare clic su <STRONG>Configurazione pool</STRONG> se si desidera che la configurazione venga applicata a un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="09e76-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="09e76-117">In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="09e76-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="09e76-118">In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09e76-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="09e76-p105">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.</span><span class="sxs-lookup"><span data-stu-id="09e76-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="09e76-p106">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="09e76-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="09e76-124">Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="09e76-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="09e76-125">È sempre possibile accedere al contenuto cronologico eseguendo una ricerca.</span><span class="sxs-lookup"><span data-stu-id="09e76-125">You can always access historical content by search.</span></span> <span data-ttu-id="09e76-126">Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.</span><span class="sxs-lookup"><span data-stu-id="09e76-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="09e76-p108">In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.</span><span class="sxs-lookup"><span data-stu-id="09e76-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="09e76-130">Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che utilizzano Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat possono inserire file in una sala.</span><span class="sxs-lookup"><span data-stu-id="09e76-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="09e76-131">Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="09e76-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="09e76-132">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="09e76-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="09e76-133">Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="09e76-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="09e76-134">Per impostazione predefinita, questo valore è pari a 75.</span><span class="sxs-lookup"><span data-stu-id="09e76-134">By default, the number is 75.</span></span> <span data-ttu-id="09e76-135">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="09e76-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="09e76-p111">(Facoltativo) In **URL gestione chat** selezionare l'URL di gestione chat. Si tratta dell'URL per una gestione chat personalizzata basata sul Web. Se non è necessario personalizzare la gestione chat, e si utilizza semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo l'impostazione, l'URL viene applicato come URL di gestione chat interno ed esterno.</span><span class="sxs-lookup"><span data-stu-id="09e76-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="09e76-140">Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL.</span><span class="sxs-lookup"><span data-stu-id="09e76-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="09e76-141">Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.</span><span class="sxs-lookup"><span data-stu-id="09e76-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="09e76-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="09e76-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="09e76-143">Per configurare le opzioni di chat persistente per un pool di server Chat persistente specifico</span><span class="sxs-lookup"><span data-stu-id="09e76-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="09e76-144">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="09e76-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="09e76-145">Scegliere il pannello di controllo di Lync Server dal menu **Start** oppure aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="09e76-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="09e76-146">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09e76-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="09e76-147">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09e76-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="09e76-148">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09e76-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="09e76-149">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="09e76-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="09e76-150">Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="09e76-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="09e76-151">In **Seleziona un servizio**selezionare il servizio associato al pool di server Chat persistente da configurare.</span><span class="sxs-lookup"><span data-stu-id="09e76-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="09e76-152">In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09e76-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="09e76-p115">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.</span><span class="sxs-lookup"><span data-stu-id="09e76-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="09e76-p116">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="09e76-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="09e76-158">Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="09e76-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="09e76-159">È sempre possibile accedere al contenuto cronologico eseguendo una ricerca.</span><span class="sxs-lookup"><span data-stu-id="09e76-159">You can always access historical content by search.</span></span> <span data-ttu-id="09e76-160">Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.</span><span class="sxs-lookup"><span data-stu-id="09e76-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="09e76-p118">In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.</span><span class="sxs-lookup"><span data-stu-id="09e76-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="09e76-164">Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti (Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat) possono inserire file in una sala.</span><span class="sxs-lookup"><span data-stu-id="09e76-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="09e76-165">Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="09e76-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="09e76-166">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="09e76-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="09e76-167">Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="09e76-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="09e76-168">Per impostazione predefinita, questo valore è pari a 75.</span><span class="sxs-lookup"><span data-stu-id="09e76-168">By default, the number is 75.</span></span> <span data-ttu-id="09e76-169">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="09e76-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="09e76-p121">In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL.</span><span class="sxs-lookup"><span data-stu-id="09e76-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="09e76-173">Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL.</span><span class="sxs-lookup"><span data-stu-id="09e76-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="09e76-174">Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="09e76-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="09e76-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="09e76-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

