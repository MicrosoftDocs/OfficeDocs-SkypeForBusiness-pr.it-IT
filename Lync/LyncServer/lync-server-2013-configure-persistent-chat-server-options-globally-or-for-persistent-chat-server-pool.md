---
title: 'Lync Server 2013: Configurare le opzioni del server chat persistente a livello globale o per il pool di server chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed79d1144c1ccb7abeac8dcf7d1f4d44c63e93e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="3ad06-102">Configurare le opzioni del server chat persistente a livello globale o per il pool di server chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ad06-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ad06-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3ad06-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3ad06-104">Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione configurazione della chat **persistente** della pagina della **chat** persistente per configurare le impostazioni della chat persistente a livello globale, dove si applica a tutti i pool di server di chat permanenti o per un pool di server di chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="3ad06-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ad06-105">Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="3ad06-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="3ad06-106">Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3ad06-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="3ad06-107">Per configurare le opzioni di chat persistenti a livello globale</span><span class="sxs-lookup"><span data-stu-id="3ad06-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="3ad06-108">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3ad06-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ad06-109">Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3ad06-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="3ad06-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ad06-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ad06-111">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ad06-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="3ad06-112">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3ad06-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="3ad06-113">Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="3ad06-114">Nella pagina di **configurazione della chat persistente** fare clic su **nuovo** e quindi su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ad06-115">Scegliere questa opzione se si vuole che la configurazione venga applicata a tutti i pool di server di chat persistenti distribuiti nel sito.</span><span class="sxs-lookup"><span data-stu-id="3ad06-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="3ad06-116">Fare clic su <STRONG>Configurazione pool</STRONG> se si vuole che la configurazione venga applicata a un pool di server di chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="3ad06-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="3ad06-117">In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3ad06-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="3ad06-118">In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ad06-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="3ad06-p105">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="3ad06-p106">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="3ad06-124">Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="3ad06-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="3ad06-125">È sempre possibile accedere al contenuto cronologico tramite ricerca.</span><span class="sxs-lookup"><span data-stu-id="3ad06-125">You can always access historical content by search.</span></span> <span data-ttu-id="3ad06-126">Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room.</span><span class="sxs-lookup"><span data-stu-id="3ad06-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="3ad06-p108">In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).</span><span class="sxs-lookup"><span data-stu-id="3ad06-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="3ad06-130">Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che usano Office Communications Server&nbsp;2007 R2 Group Chat Server o Lync Server 2010, Group Chat possono pubblicare file in una sala.</span><span class="sxs-lookup"><span data-stu-id="3ad06-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="3ad06-131">Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3ad06-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="3ad06-132">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3ad06-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="3ad06-133">Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="3ad06-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="3ad06-134">Per impostazione predefinita, il numero è 75.</span><span class="sxs-lookup"><span data-stu-id="3ad06-134">By default, the number is 75.</span></span> <span data-ttu-id="3ad06-135">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="3ad06-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="3ad06-p111">(Facoltativo.) In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="3ad06-140">Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="3ad06-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="3ad06-141">Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3ad06-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="3ad06-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="3ad06-143">Per configurare le opzioni di chat persistenti per un pool di server di chat persistente specifico</span><span class="sxs-lookup"><span data-stu-id="3ad06-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="3ad06-144">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3ad06-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ad06-145">Nel menu **Start** selezionare il pannello di controllo di Lync Server oppure aprire una finestra del browser e quindi immettere l'URL dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3ad06-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="3ad06-146">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ad06-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3ad06-147">È anche possibile usare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ad06-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="3ad06-148">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3ad06-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="3ad06-149">Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="3ad06-150">Nella pagina **Configurazione di Chat persistente** fare clic su **Nuovo** e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="3ad06-151">In **Seleziona un servizio**selezionare il servizio associato al pool di server di chat persistente da configurare.</span><span class="sxs-lookup"><span data-stu-id="3ad06-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="3ad06-152">In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ad06-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="3ad06-p115">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool esiste già.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="3ad06-p116">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="3ad06-158">Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="3ad06-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="3ad06-159">È sempre possibile accedere al contenuto cronologico tramite ricerca.</span><span class="sxs-lookup"><span data-stu-id="3ad06-159">You can always access historical content by search.</span></span> <span data-ttu-id="3ad06-160">Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room.</span><span class="sxs-lookup"><span data-stu-id="3ad06-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="3ad06-p118">In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).</span><span class="sxs-lookup"><span data-stu-id="3ad06-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="3ad06-164">Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti (Office Communications Server 2007&nbsp;R2 Group Chat Server o Lync Server 2010, Group Chat) possono pubblicare file in una sala.</span><span class="sxs-lookup"><span data-stu-id="3ad06-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="3ad06-165">Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3ad06-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="3ad06-166">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3ad06-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="3ad06-167">Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="3ad06-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="3ad06-168">Per impostazione predefinita, il numero è 75.</span><span class="sxs-lookup"><span data-stu-id="3ad06-168">By default, the number is 75.</span></span> <span data-ttu-id="3ad06-169">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="3ad06-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="3ad06-p121">In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL.</span><span class="sxs-lookup"><span data-stu-id="3ad06-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="3ad06-173">Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="3ad06-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="3ad06-174">Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3ad06-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="3ad06-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3ad06-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

