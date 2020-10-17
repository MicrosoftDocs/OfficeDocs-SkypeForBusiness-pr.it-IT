---
title: 'Lync Server 2013: configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente'
description: 'Lync Server 2013: configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente.'
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
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564992"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="7baf6-103">Configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7baf6-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7baf6-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="7baf6-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="7baf6-105">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la sezione **configurazione di Persistent Chat** della pagina **chat** persistente per configurare le impostazioni di chat persistente a livello globale in cui si applica a tutti i pool di server Chat persistente o per un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="7baf6-105">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7baf6-106">Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="7baf6-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="7baf6-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7baf6-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="7baf6-108">Per configurare le opzioni di chat persistente a livello globale</span><span class="sxs-lookup"><span data-stu-id="7baf6-108">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="7baf6-109">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7baf6-109">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7baf6-110">Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7baf6-110">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7baf6-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7baf6-111">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7baf6-112">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7baf6-112">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7baf6-113">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7baf6-113">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7baf6-114">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="7baf6-115">Nella pagina **Configurazione Persistent Chat** fare clic su **nuovo** e quindi su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-115">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7baf6-116">Scegliere questa opzione se si desidera che la configurazione venga applicata a tutti i pool di server Chat persistente distribuiti nel sito.</span><span class="sxs-lookup"><span data-stu-id="7baf6-116">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="7baf6-117">Fare clic su <STRONG>Configurazione pool</STRONG> se si desidera che la configurazione venga applicata a un pool di server Chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="7baf6-117">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="7baf6-118">In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7baf6-118">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="7baf6-119">In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7baf6-119">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="7baf6-p105">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="7baf6-p106">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7baf6-125">Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="7baf6-125">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="7baf6-126">È sempre possibile accedere al contenuto cronologico eseguendo una ricerca.</span><span class="sxs-lookup"><span data-stu-id="7baf6-126">You can always access historical content by search.</span></span> <span data-ttu-id="7baf6-127">Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.</span><span class="sxs-lookup"><span data-stu-id="7baf6-127">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7baf6-p108">In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7baf6-131">Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che utilizzano Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat possono inserire file in una sala.</span><span class="sxs-lookup"><span data-stu-id="7baf6-131">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="7baf6-132">Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7baf6-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7baf6-133">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7baf6-133">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="7baf6-134">Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="7baf6-134">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="7baf6-135">Per impostazione predefinita, questo valore è pari a 75.</span><span class="sxs-lookup"><span data-stu-id="7baf6-135">By default, the number is 75.</span></span> <span data-ttu-id="7baf6-136">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="7baf6-136">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="7baf6-p111">(Facoltativo) In **URL gestione chat** selezionare l'URL di gestione chat. Si tratta dell'URL per una gestione chat personalizzata basata sul Web. Se non è necessario personalizzare la gestione chat, e si utilizza semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo l'impostazione, l'URL viene applicato come URL di gestione chat interno ed esterno.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="7baf6-141">Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL.</span><span class="sxs-lookup"><span data-stu-id="7baf6-141">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="7baf6-142">Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7baf6-142">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="7baf6-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="7baf6-144">Per configurare le opzioni di chat persistente per un pool di server Chat persistente specifico</span><span class="sxs-lookup"><span data-stu-id="7baf6-144">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="7baf6-145">Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7baf6-145">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7baf6-146">Scegliere il pannello di controllo di Lync Server dal menu **Start** oppure aprire una finestra del browser e quindi immettere l'URL di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7baf6-146">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="7baf6-147">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7baf6-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7baf6-148">È inoltre possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7baf6-148">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7baf6-149">Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7baf6-149">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="7baf6-150">Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-150">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="7baf6-151">Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-151">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="7baf6-152">In **Seleziona un servizio**selezionare il servizio associato al pool di server Chat persistente da configurare.</span><span class="sxs-lookup"><span data-stu-id="7baf6-152">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="7baf6-153">In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7baf6-153">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="7baf6-p115">In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="7baf6-p116">In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7baf6-159">Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="7baf6-159">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="7baf6-160">È sempre possibile accedere al contenuto cronologico eseguendo una ricerca.</span><span class="sxs-lookup"><span data-stu-id="7baf6-160">You can always access historical content by search.</span></span> <span data-ttu-id="7baf6-161">Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.</span><span class="sxs-lookup"><span data-stu-id="7baf6-161">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7baf6-p118">In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="7baf6-165">Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti (Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat) possono inserire file in una sala.</span><span class="sxs-lookup"><span data-stu-id="7baf6-165">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="7baf6-166">Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7baf6-166">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="7baf6-167">In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7baf6-167">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="7baf6-168">Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero.</span><span class="sxs-lookup"><span data-stu-id="7baf6-168">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="7baf6-169">Per impostazione predefinita, questo valore è pari a 75.</span><span class="sxs-lookup"><span data-stu-id="7baf6-169">By default, the number is 75.</span></span> <span data-ttu-id="7baf6-170">Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.</span><span class="sxs-lookup"><span data-stu-id="7baf6-170">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="7baf6-p121">In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL.</span><span class="sxs-lookup"><span data-stu-id="7baf6-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="7baf6-174">Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL.</span><span class="sxs-lookup"><span data-stu-id="7baf6-174">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="7baf6-175">Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7baf6-175">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="7baf6-176">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7baf6-176">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

