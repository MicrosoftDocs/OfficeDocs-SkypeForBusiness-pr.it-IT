---
title: Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 311472459958a60708e89a4eace22e5ace1325cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="5a4ae-102">Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a4ae-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a4ae-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a4ae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a4ae-104">Lo strumento di filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Lync Server 2013 in base alla diffusione delle forme più comuni di virus con riduzione minima dell'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="5a4ae-105">Utilizzare il filtro di protezione per messaggi istantanei per configurare filtri per bloccare i messaggi istantanei indesiderati o potenzialmente pericolosi provenienti da endpoint sconosciuti esterni al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="5a4ae-106">È possibile configurare i filtri specificando i criteri da utilizzare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali con prefissi specifici e file con estensioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="5a4ae-107">Il filtro di protezione per messaggi istantanei offre le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="5a4ae-108">Filtro avanzato per gli URL</span><span class="sxs-lookup"><span data-stu-id="5a4ae-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="5a4ae-109">Filtro avanzato per il trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="5a4ae-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="5a4ae-110">La configurazione del filtro di protezione per messaggi istantanei prevede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="5a4ae-111">Configurazione del filtro per gli URL</span><span class="sxs-lookup"><span data-stu-id="5a4ae-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="5a4ae-112">Configurazione del filtro per il trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="5a4ae-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="5a4ae-113">Modalità di applicazione delle opzioni di filtro ai messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="5a4ae-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="5a4ae-114">Prima di distribuire lo strumento di filtro dei messaggi di messaggistica istantanea intelligente, è necessario comprendere il modo in cui vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server Lync Server 2013 a un altro.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="5a4ae-115">Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in una singola organizzazione oppure oltre i limiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="5a4ae-116">Tale coerenza si applica al modo in cui i testi delle note e degli avvisi personalizzati vengono inseriti nei messaggi e inviati tra server.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5a4ae-117">Il filtro di protezione per messaggi istantanei comporta un aumento della quantità di risorse CPU necessarie per elaborare gli URL in un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="5a4ae-118">Questo aumento della richiesta di CPU influisce anche sulle prestazioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="5a4ae-119">Utilizzando la pagina **filtro URL** nel gruppo di **messaggistica istantanea e presenza** nel pannello di controllo di Lync Server, è possibile bloccare alcuni o tutti i collegamenti ipertestuali o configurare un avviso.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="5a4ae-120">L'avviso viene inserito all'inizio di un messaggio istantaneo contenente un collegamento ipertestuale quando per **Prefisso di collegamento ipertestuale** si seleziona l'opzione **Invia messaggio di avviso**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="5a4ae-121">Quando un messaggio istantaneo passa da un server a un altro, si applicano le linee guida generali seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="5a4ae-p105">Se un server blocca un messaggio istantaneo (perché è stata selezionata la casella di controllo **Blocca URL con estensione di file** nella pagina **Filtro URL** o perché per **Prefisso di collegamento ipertestuale** è stata selezionata l'opzione **Blocca collegamenti ipertestuali**), al client viene restituito un messaggio di errore. I server successivi non ricevono il messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="5a4ae-p106">Se un server (Server1) aggiunge un avviso a un messaggio istantaneo contenente un collegamento ipertestuale attivo, un server successivo (Server2) che riceve il messaggio istantaneo può comunque eseguire un'azione diversa in base a tale collegamento ipertestuale attivo presente nel messaggio istantaneo e bloccare il messaggio o aggiungere un avviso. Se Server2 è configurato solo per aggiungere un avviso per l'URL, il precedente avviso aggiunto da Server1 viene rimosso e quello configurato in Server2 viene aggiunto all'inizio del messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5a4ae-126">Se Lync Server 2013 è in esecuzione in un ambiente misto, Live Communications Server 2005 con SP1 è la versione minima necessaria per utilizzare l'applicazione filtro di messaggistica istantanea intelligente.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="5a4ae-127">Il filtro di protezione per messaggi istantanei non è supportato su Live Communications Server 2005 senza SP1.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="5a4ae-128">Filtro per gli URL</span><span class="sxs-lookup"><span data-stu-id="5a4ae-128">URL Filtering</span></span>

<span data-ttu-id="5a4ae-p108">Gli URL vengono filtrati in base al relativo prefisso di collegamento ipertestuale. Gli esempi seguenti sono prefissi validi:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="5a4ae-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-131">www\*.</span></span>

  - <span data-ttu-id="5a4ae-132">FTP.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-132">ftp.</span></span>

  - <span data-ttu-id="5a4ae-133">http</span><span class="sxs-lookup"><span data-stu-id="5a4ae-133">http:</span></span>

<span data-ttu-id="5a4ae-p109">Se non si configura il filtro per messaggi istantanei in modo da filtrare gli URL, tutti gli URL presenti nei messaggi istantanei verranno passati attraverso il server senza essere modificati. Se si configura il filtro per messaggi istantanei in modo da filtrare gli URL, gli URL presenti nei messaggi istantanei verranno filtrati in base alle opzioni selezionate nella finestra di dialogo **Modifica filtro URL** o **Crea nuovo filtro URL**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="5a4ae-136">**Abilita filtro**   URL questa opzione consente di abilitare il filtro URL per la distribuzione globale o per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="5a4ae-137">**Blocca URL con estensione**   file il filtro messaggi istantanei blocca qualsiasi URL Internet o Intranet attivo contenente un file con un'estensione elencata in **estensioni di file da bloccare** nella finestra di dialogo **Modifica filtro file** .</span><span class="sxs-lookup"><span data-stu-id="5a4ae-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="5a4ae-138">Quando un URL viene bloccato, al mittente viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="5a4ae-139">Se viene selezionata, questa opzione ha la precedenza su tutte le altre opzioni di filtro per le estensioni di file definite in **Estensioni di file da bloccare**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5a4ae-140">Il filtro delle estensioni di file è limitato ai nomi file standard.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="5a4ae-141">Il filtro potrebbe non funzionare con estensioni di file incorporate in altri nomi.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="5a4ae-142">Per configurare la modalità con cui vengono gestiti i collegamenti ipertestuali nelle conversazioni istantanee, selezionare una delle opzioni seguenti in **Prefisso di collegamento ipertestuale**:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="5a4ae-143">**Non filtrare**   gli URL nei messaggi inviati tramite il server.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="5a4ae-144">Quando si seleziona questa opzione, viene visualizzata la casella **Consenti messaggio**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="5a4ae-145">In tale** **casella specificare la nota che si desidera inserire all'inizio di ogni messaggio istantaneo contenente collegamenti ipertestuali.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="5a4ae-146">Questa nota può essere costituita al massimo da 65535 caratteri.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="5a4ae-147">**Blocca collegamenti ipertestuali**   il recapito dei messaggi istantanei contenenti collegamenti ipertestuali attivi è bloccato da Lync Server e viene visualizzato un messaggio di errore al mittente.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="5a4ae-148">**Invia messaggio**   di avviso Lync Server consente collegamenti ipertestuali attivi nei messaggi istantanei, ma include un avviso.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="5a4ae-149">Quando si seleziona questa opzione, viene visualizzata la casella **Messaggio di avviso**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="5a4ae-150">In tale** **casella è necessario digitare l'avviso che si desidera inserire nei messaggi istantanei contenenti collegamenti ipertestuali validi.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="5a4ae-151">L'avviso ad esempio potrebbe segnalare i pericoli che si possono correre facendo clic su un collegamento sconosciuto o fare riferimento ai requisiti e ai criteri pertinenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="5a4ae-152">Questo avviso può essere costituito al massimo da 65535 caratteri.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="5a4ae-153">Se si seleziona **Blocca collegamenti ipertestuali** o **Invia messaggio di avviso**, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="5a4ae-154">**Escludi collegamenti ipertestuali Intranet locali**   il filtro dei messaggi istantanei blocca solo gli URL Internet.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="5a4ae-155">Gli URL relativi ai percorsi all'interno della rete Intranet vengono passati attraverso il server senza essere modificati.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="5a4ae-156">Tuttavia, gli URL Intranet che i singoli server che eseguono Lync Server pass dipendono da quali tipi di siti Web locali sono considerati parte dell'area Intranet.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="5a4ae-157">Per verificare le impostazioni dell'area Intranet del server, vedere la procedura "per configurare le impostazioni della rete Intranet in Internet Explorer" in [Modify the default URL Filter in Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="5a4ae-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="5a4ae-158">**Filtrare questi**   prefissi di collegamento ipertestuale per scegliere quali prefissi si desidera bloccare, fare clic su **Seleziona**e quindi in **Seleziona prefisso collegamento**ipertestuale aggiungere i prefissi all'elenco **prefissi di collegamento ipertestuale** .</span><span class="sxs-lookup"><span data-stu-id="5a4ae-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="5a4ae-159">Tutti i prefissi, ad eccezione di **href**, devono terminare con un punto o i due punti oppure con un asterisco seguito da un punto.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="5a4ae-160">I prefissi validi possono contenere tutti i caratteri del set di caratteri URL validi, ad eccezione\*dell'asterisco ().</span><span class="sxs-lookup"><span data-stu-id="5a4ae-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="5a4ae-161">Il set di caratteri URL validi è: \# \*+/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` abcdefghijklmnopqrstuvwxyz | ~</span><span class="sxs-lookup"><span data-stu-id="5a4ae-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="5a4ae-162">Filtro per il trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="5a4ae-162">File Transfer Filtering</span></span>

<span data-ttu-id="5a4ae-p116">Il filtro per il trasferimento di file riguarda sia i messaggi istantanei che le conferenze. Per le conferenze, queste impostazioni influiscono sia sulla funzionalità relativa agli stampati del client Office Live Meeting 2007 che sulle funzionalità di riproduzione multimediale.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5a4ae-165">Lync Server offre anche opzioni di impostazione del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="5a4ae-166">Questa opzione sul server viene offerta oltre ai controlli sul retro disponibili in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="5a4ae-p118">È possibile filtrare i trasferimenti di file durante le conversazioni istantanee, quando si utilizza la funzionalità relativa agli stampati del client Office Live Meeting 2007 e per le funzionalità di riproduzione multimediale per tutti i tipi di file. Per controllare i trasferimenti di file, è possibile impostare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="5a4ae-169">**Attiva filtro**   file questa opzione consente di abilitare il filtro dei file per la distribuzione globale o per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="5a4ae-170">Quando si abilita il filtro per i file, è possibile selezionare una delle opzioni seguenti in **Trasferimento file**:</span><span class="sxs-lookup"><span data-stu-id="5a4ae-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="5a4ae-171">**Blocca tipi**   di file specifici specificare le richieste di trasferimento dei file filtrate dal server specificando un elenco di estensioni di file da bloccare.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="5a4ae-172">Le voci nell'elenco possono contenere tutti i caratteri standard, ma non il carattere jolly\*().</span><span class="sxs-lookup"><span data-stu-id="5a4ae-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="5a4ae-173">Nel client Office Live Meeting 2007 la funzionalità relativa agli stampati sarà abilitata, ma i file con le estensioni specificate non potranno essere caricati o scaricati.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="5a4ae-174">Se si seleziona la casella di controllo **Blocca URL con estensione di file** nelle impostazioni di un filtro per gli URL nella scheda **Filtro URL**, tale filtro utilizzerà questo stesso elenco per bloccare i collegamenti ipertestuali attivi contenenti una qualsiasi di queste estensioni di file.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="5a4ae-175">Per specificare quali tipi di file bloccare, fare clic su **Seleziona** e quindi in **Seleziona estensioni di file** aggiungere le estensioni di file desiderate all'elenco **Estensioni di file selezionate**.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="5a4ae-176">**Blocca tutto**   il server rilascia tutti i messaggi istantanei che contengono richieste di trasferimento di file e restituisce un messaggio di errore al mittente della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="5a4ae-177">La funzionalità relativa agli stampati del client Office Live Meeting 2007 sarà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5a4ae-p121">Il filtro delle estensioni di file è limitato ai nomi file standard. Il filtro potrebbe non funzionare con estensioni di file incorporate in altri nomi.</span><span class="sxs-lookup"><span data-stu-id="5a4ae-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a4ae-180">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5a4ae-180">In This Section</span></span>

  - [<span data-ttu-id="5a4ae-181">Modificare il filtro di trasferimento file predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a4ae-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="5a4ae-182">Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="5a4ae-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="5a4ae-183">Modificare il filtro URL predefinito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a4ae-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="5a4ae-184">Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="5a4ae-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a4ae-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a4ae-185">See Also</span></span>


[<span data-ttu-id="5a4ae-186">Gestione delle impostazioni di messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a4ae-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

