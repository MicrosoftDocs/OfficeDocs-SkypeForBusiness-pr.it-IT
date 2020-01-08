---
title: Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="b4088-102">Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4088-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4088-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b4088-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b4088-104">Lo strumento di filtro ISTANTANEo intelligente consente di proteggere la distribuzione di Lync Server 2013 con la diffusione delle forme più comuni di virus con una degradazione minima dell'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="b4088-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="b4088-105">Usare il filtro istantaneo intelligente per configurare i filtri per bloccare i messaggi istantanei non richiesti o potenzialmente nocivi da endpoint sconosciuti esterni al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="b4088-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="b4088-106">I filtri vengono configurati specificando i criteri da usare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali con prefissi e file specifici con specifiche estensioni.</span><span class="sxs-lookup"><span data-stu-id="b4088-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="b4088-107">Il filtro ISTANTANEo intelligente offre gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4088-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="b4088-108">Filtro di URL avanzato.</span><span class="sxs-lookup"><span data-stu-id="b4088-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="b4088-109">Filtro di trasferimento file avanzato.</span><span class="sxs-lookup"><span data-stu-id="b4088-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="b4088-110">La configurazione di un filtro ISTANTANEo intelligente include le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4088-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="b4088-111">Configurazione del filtro URL.</span><span class="sxs-lookup"><span data-stu-id="b4088-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="b4088-112">Configurazione del filtro trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="b4088-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="b4088-113">Come vengono applicate le opzioni di filtro ai messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="b4088-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="b4088-114">Prima di distribuire lo strumento di filtro messaggi ISTANTANEi intelligente, è necessario capire in che modo le opzioni di filtro vengono applicate quando i messaggi vengono instradati da un server di Lync Server 2013 a un altro.</span><span class="sxs-lookup"><span data-stu-id="b4088-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="b4088-115">Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in un'unica organizzazione o in tutti i confini aziendali.</span><span class="sxs-lookup"><span data-stu-id="b4088-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="b4088-116">Questa coerenza si applica al modo in cui i testi personalizzati di avviso e di avviso vengono inseriti nei messaggi e inviati attraverso i server.</span><span class="sxs-lookup"><span data-stu-id="b4088-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b4088-117">Il filtro dei messaggi istantanei aumenta la quantità di risorse della CPU necessarie per elaborare gli URL in un messaggio.</span><span class="sxs-lookup"><span data-stu-id="b4088-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="b4088-118">Questo aumento della richiesta di CPU influenza anche le prestazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4088-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="b4088-119">Usando la pagina **filtro URL** nel gruppo **messaggistica istantanea e presenza** del pannello di controllo di Lync Server, è possibile bloccare alcuni o tutti i collegamenti ipertestuali o configurare un avviso.</span><span class="sxs-lookup"><span data-stu-id="b4088-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="b4088-120">L'avviso viene inserito all'inizio di un messaggio istantaneo che contiene un collegamento ipertestuale quando si sceglie l'opzione **Invia messaggio di avviso**per il **prefisso del collegamento ipertestuale** .</span><span class="sxs-lookup"><span data-stu-id="b4088-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="b4088-121">Quando un messaggio istantaneo viaggia da un server a un altro, si applicano le linee guida generali seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4088-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="b4088-122">Se un server blocca un messaggio istantaneo, perché è stata selezionata la casella di controllo **Blocca URL con estensione file** nella pagina **filtro URL** o perché si è scelto l'opzione **prefisso collegamento ipertestuale** per **bloccare i collegamenti ipertestuali**, viene restituito un messaggio di errore al client.</span><span class="sxs-lookup"><span data-stu-id="b4088-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="b4088-123">I server successivi non ricevono questo messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="b4088-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="b4088-124">Se un server (Server1) aggiunge un avviso a un messaggio istantaneo che contiene un collegamento ipertestuale attivo, un server successivo (Server2) che riceve questo messaggio istantaneo può comunque eseguire un'azione diversa in base a questo collegamento ipertestuale attivo presente nel messaggio istantaneo e bloccare l' messaggio istantaneo o aggiunta di un avviso.</span><span class="sxs-lookup"><span data-stu-id="b4088-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="b4088-125">Se Server2 è configurato solo per aggiungere un avviso per questo URL, l'avviso precedente aggiunto da Server1 viene rimosso e l'avviso configurato su Server2 viene aggiunto all'inizio del messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="b4088-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b4088-126">Se si esegue Lync Server 2013 in un ambiente misto, Live Communications Server 2005 con SP1 è la versione minima necessaria per usare l'applicazione di filtro messaggi istantanei intelligente.</span><span class="sxs-lookup"><span data-stu-id="b4088-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="b4088-127">Il filtro di messaggistica istantanea intelligente non è supportato in Live Communications Server 2005 senza SP1.</span><span class="sxs-lookup"><span data-stu-id="b4088-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="b4088-128">Filtro URL</span><span class="sxs-lookup"><span data-stu-id="b4088-128">URL Filtering</span></span>

<span data-ttu-id="b4088-129">Gli URL vengono filtrati in base al prefisso del collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="b4088-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="b4088-130">Gli esempi seguenti sono prefissi validi:</span><span class="sxs-lookup"><span data-stu-id="b4088-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="b4088-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="b4088-131">www\*.</span></span>

  - <span data-ttu-id="b4088-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="b4088-132">ftp.</span></span>

  - <span data-ttu-id="b4088-133">http</span><span class="sxs-lookup"><span data-stu-id="b4088-133">http:</span></span>

<span data-ttu-id="b4088-134">Se non si configura il filtro per i messaggi istantanei per eseguire il filtro degli URL, tutti gli URL contenuti nei messaggi istantanei vengono passati non modificati tramite il server.</span><span class="sxs-lookup"><span data-stu-id="b4088-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="b4088-135">Se si configura il filtro dei messaggi istantanei per eseguire il filtro URL, gli URL nei messaggi istantanei vengono filtrati in base alle opzioni selezionate nella finestra di dialogo **Modifica filtro URL** o **nuovo filtro URL** .</span><span class="sxs-lookup"><span data-stu-id="b4088-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="b4088-136">**Abilita filtro**   URL questa opzione consente di filtrare gli URL per la distribuzione globale o per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="b4088-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="b4088-137">**Bloccare gli URL con estensione**   di file il filtro messaggi istantanei blocca qualsiasi URL Intranet o Internet attivo che contiene un file con un'estensione elencata in **estensioni di file da bloccare** nella finestra di dialogo **Modifica filtro file** .</span><span class="sxs-lookup"><span data-stu-id="b4088-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="b4088-138">Quando un URL è bloccato, al mittente viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b4088-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="b4088-139">Se selezionata, questa opzione ha la precedenza su tutte le altre opzioni di filtro per tutte le estensioni di file definite in **estensioni di file da bloccare**.</span><span class="sxs-lookup"><span data-stu-id="b4088-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b4088-140">Il filtro delle estensioni di file è limitato ai nomi di file standard.</span><span class="sxs-lookup"><span data-stu-id="b4088-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="b4088-141">Il filtro potrebbe non funzionare con le estensioni di file incorporate in altri nomi.</span><span class="sxs-lookup"><span data-stu-id="b4088-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="b4088-142">Per configurare la modalità di gestione dei collegamenti ipertestuali nelle conversazioni di messaggistica istantanea, selezionare una delle opzioni seguenti in **prefisso collegamento ipertestuale**:</span><span class="sxs-lookup"><span data-stu-id="b4088-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="b4088-143">**Non filtrare**   gli URL nei messaggi inviati tramite il server.</span><span class="sxs-lookup"><span data-stu-id="b4088-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="b4088-144">Quando si sceglie questa opzione, viene visualizzata la casella **Consenti messaggio** .</span><span class="sxs-lookup"><span data-stu-id="b4088-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="b4088-145">Nella casella **Consenti messaggio** specificare l'avviso che si vuole inserire all'inizio di ogni messaggio istantaneo contenente collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="b4088-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="b4088-146">Questo avviso può essere costituito da non più di 65535 caratteri.</span><span class="sxs-lookup"><span data-stu-id="b4088-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="b4088-147">**Blocca collegamenti ipertestuali**   il recapito dei messaggi istantanei contenenti collegamenti ipertestuali attivi viene bloccato da Lync Server e viene visualizzato un messaggio di errore al mittente.</span><span class="sxs-lookup"><span data-stu-id="b4088-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="b4088-148">**Invia messaggio**   di avviso Lync Server consente collegamenti ipertestuali attivi nei messaggi istantanei, ma include un avviso.</span><span class="sxs-lookup"><span data-stu-id="b4088-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="b4088-149">Quando si sceglie questa opzione, viene visualizzata la finestra di **messaggio di avviso** .</span><span class="sxs-lookup"><span data-stu-id="b4088-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="b4088-150">Nella casella **messaggio di avviso** è necessario digitare l'avviso che si desidera includere nei messaggi istantanei contenenti collegamenti ipertestuali validi.</span><span class="sxs-lookup"><span data-stu-id="b4088-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="b4088-151">Ad esempio, questo avviso potrebbe indicare i potenziali pericoli di fare clic su un collegamento sconosciuto oppure può fare riferimento ai criteri e ai requisiti pertinenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4088-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="b4088-152">L'avviso non può essere maggiore di 65535 caratteri.</span><span class="sxs-lookup"><span data-stu-id="b4088-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="b4088-153">Se si seleziona **Blocca collegamenti ipertestuali** o **Invia messaggio di avviso**, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4088-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="b4088-154">**Escludi collegamenti ipertestuali Intranet locali**   il filtro per i messaggi istantanei blocca solo gli URL Internet.</span><span class="sxs-lookup"><span data-stu-id="b4088-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="b4088-155">Gli URL per le posizioni all'interno della Intranet vengono passati non modificati tramite il server.</span><span class="sxs-lookup"><span data-stu-id="b4088-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="b4088-156">Tuttavia, gli URL Intranet che i singoli server che esegue Lync Server passano dipendono dai tipi di siti Web locali considerati parte dell'area Intranet.</span><span class="sxs-lookup"><span data-stu-id="b4088-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="b4088-157">Per controllare le impostazioni dell'area Intranet del server, vedere la procedura "per configurare le impostazioni della Intranet in Internet Explorer" in [modificare il filtro URL predefinito in Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="b4088-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="b4088-158">**Filtrare questi prefissi dei collegamenti ipertestuali**   per scegliere i prefissi da bloccare, fare clic su **Seleziona**e quindi, in **Seleziona prefisso collegamento**ipertestuale, aggiungere i prefissi all'elenco **prefissi collegamento ipertestuale** .</span><span class="sxs-lookup"><span data-stu-id="b4088-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="b4088-159">Tutti i prefissi eccetto **href** devono terminare con un punto o due punti oppure un asterisco seguito da un punto.</span><span class="sxs-lookup"><span data-stu-id="b4088-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="b4088-160">I prefissi validi possono contenere qualsiasi carattere nel set di caratteri URL validi eccetto l'asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="b4088-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="b4088-161">Il set di caratteri validi per gli URL \# \*è: +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="b4088-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="b4088-162">Filtro trasferimento file</span><span class="sxs-lookup"><span data-stu-id="b4088-162">File Transfer Filtering</span></span>

<span data-ttu-id="b4088-163">Filtro trasferimento filtri influisce su messaggi istantanei e conferenze.</span><span class="sxs-lookup"><span data-stu-id="b4088-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="b4088-164">Per le conferenze, queste impostazioni influiscono sulla caratteristica stampati nel client di Office Live Meeting 2007 e nelle funzionalità di riproduzione multimediale.</span><span class="sxs-lookup"><span data-stu-id="b4088-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b4088-165">Lync Server offre anche opzioni per l'impostazione del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="b4088-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="b4088-166">Questa opzione lato server è disponibile oltre ai controlli lato client disponibili in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4088-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="b4088-167">È possibile filtrare i trasferimenti di file durante le conversazioni istantanee, quando si usa la caratteristica stampati nel client Office Live Meeting 2007 e per le funzionalità di riproduzione multimediale per tutti i tipi di file.</span><span class="sxs-lookup"><span data-stu-id="b4088-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="b4088-168">È possibile impostare le opzioni seguenti per controllare i trasferimenti di file:</span><span class="sxs-lookup"><span data-stu-id="b4088-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="b4088-169">**Abilita filtro**   file questa opzione consente di filtrare i file per la distribuzione globale o per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="b4088-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="b4088-170">Quando si Abilita il filtro file, è possibile scegliere una delle opzioni seguenti in **trasferimento file**:</span><span class="sxs-lookup"><span data-stu-id="b4088-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="b4088-171">**Blocca tipi**   di file specifici per specificare quali richieste di trasferimento di file vengono filtrate dal server specificando un elenco di estensioni di file da bloccare.</span><span class="sxs-lookup"><span data-stu-id="b4088-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="b4088-172">Le voci nell'elenco possono contenere tutti i caratteri standard, ma non il carattere jolly\*().</span><span class="sxs-lookup"><span data-stu-id="b4088-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="b4088-173">Nel client Office Live Meeting 2007 è abilitata la caratteristica stampati, ma non è possibile caricare o scaricare qualsiasi file con questa estensione.</span><span class="sxs-lookup"><span data-stu-id="b4088-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="b4088-174">Se si seleziona la casella di controllo **Blocca URL con estensione di file** nelle impostazioni per un filtro URL elencato nella scheda **filtro URL** , il filtro URL usa lo stesso elenco per bloccare i collegamenti ipertestuali attivi che contengono una di queste estensioni di file.</span><span class="sxs-lookup"><span data-stu-id="b4088-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="b4088-175">Per scegliere i tipi di file da bloccare, fare clic su **Seleziona**e quindi, in **Seleziona tipo di file**, aggiungere le estensioni del tipo di file all'elenco delle estensioni del **tipo di file selezionato** .</span><span class="sxs-lookup"><span data-stu-id="b4088-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="b4088-176">**Blocca tutto**   il server rilascia tutti i messaggi istantanei che contengono richieste di trasferimento di file e restituisce un messaggio di errore al mittente della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4088-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="b4088-177">La caratteristica stampati nel client Office Live Meeting 2007 è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b4088-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b4088-178">Il filtro delle estensioni di file è limitato ai nomi di file standard.</span><span class="sxs-lookup"><span data-stu-id="b4088-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="b4088-179">Il filtro potrebbe non funzionare con le estensioni di file incorporate in altri nomi.</span><span class="sxs-lookup"><span data-stu-id="b4088-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4088-180">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b4088-180">In This Section</span></span>

  - [<span data-ttu-id="b4088-181">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4088-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="b4088-182">Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="b4088-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="b4088-183">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4088-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="b4088-184">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe</span><span class="sxs-lookup"><span data-stu-id="b4088-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4088-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4088-185">See Also</span></span>


[<span data-ttu-id="b4088-186">Gestione delle impostazioni di messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4088-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

