---
title: 'Lync Server 2013: impostazioni nuove e modificate per Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="16220-102">Impostazioni nuove e modificate per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="16220-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16220-103">_**Ultimo argomento modificato:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="16220-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="16220-104">In questo argomento vengono illustrate le modifiche apportate ai cmdlet di Lync Server Management Shell correlati direttamente alla gestione client.</span><span class="sxs-lookup"><span data-stu-id="16220-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="16220-105">Lync Server 2013 introduce diversi nuovi parametri e depreca i parametri per le funzionalità che possono essere configurate con altri metodi.</span><span class="sxs-lookup"><span data-stu-id="16220-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="16220-106">Nuovi parametri di gestione client</span><span class="sxs-lookup"><span data-stu-id="16220-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16220-107">New</span><span class="sxs-lookup"><span data-stu-id="16220-107">New</span></span></th>
<th><span data-ttu-id="16220-108">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="16220-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="16220-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16220-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16220-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="16220-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="16220-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-112">Se impostato su true, l'analisi del software verrà abilitata in Lync. Se impostato su false, l'analisi del software verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="16220-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="16220-113">L'analisi del software implica la conservazione di una registrazione dettagliata di tutto ciò che un programma esegue (incluse le chiamate API di rilevamento).</span><span class="sxs-lookup"><span data-stu-id="16220-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="16220-114">L'analisi è utile principalmente per gli sviluppatori e per il personale di supporto dell'applicazione. Questa impostazione equivale all'impostazione &quot;di criteri di gruppo di Communications Server 2007 R2 attiva l'analisi per Communicator. &quot; Di seguito sono riportate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16220-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="16220-115">Off = la traccia è disabilita e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="16220-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="16220-116">Light = viene eseguita la traccia con livello minimo e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="16220-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="16220-117">On = viene eseguita la traccia con livello dettagliato e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="16220-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="16220-p103">Per impostazione predefinita, TracingLevel è impostato su un valore Null. Questo significa che verrà eseguita la traccia con livello minimo, ma che l'utente potrà abilitare o disabilitare questa traccia minima.</span><span class="sxs-lookup"><span data-stu-id="16220-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="16220-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="16220-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-p104">Se impostato su True ($True), consente la separazione dei flussi audio e video dal resto del traffico di rete. I dispositivi client possono quindi eseguire la codifica e decodifica dei dati audio e video localmente. Il reindirizzamento dei dati multimediali in genere comporta un minore utilizzo della larghezza di banda, una maggiore scalabilità dei server e un'esperienza utente più ottimizzata rispetto a tecniche simili, come la gestione remota dei dispositivi o la compressione dei codec.</span><span class="sxs-lookup"><span data-stu-id="16220-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="16220-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="16220-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="16220-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="16220-126">Se impostato su true, tutte le riunioni di Lync vengono &quot;trattate come riunioni di grandi dimensioni. &quot; Con una riunione di grandi dimensioni, vengono applicate le restrizioni sul numero di notifiche inviate ai partecipanti, oltre alle dimensioni dell'elenco di riunioni trasmesso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="16220-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="16220-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="16220-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="16220-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="16220-p105">Se impostato su True ($True), gli utenti non potranno aggiungere annotazioni alle diapositive di PowerPoint utilizzate in una conferenza. Tuttavia, a seconda del valore della proprietà AllowAnnotations, gli utenti potranno comunque accedere ad altre funzionalità della lavagna. Il valore predefinito è False, pertanto le annotazioni di PowerPoint sono consentite.</span><span class="sxs-lookup"><span data-stu-id="16220-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="16220-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="16220-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="16220-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="16220-134">Se impostato su True (valore predefinito), tutti gli eventuali blocchi appunti di OneNote aperti e collegati alla conferenza verranno aggiornati automaticamente con informazioni come i partecipanti alla conferenza e i dettagli sul contenuto condiviso durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="16220-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="16220-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="16220-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16220-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="16220-137">Utilizzato insieme agli altri nuovi parametri di CsMeetingConfiguration per personalizzare gli inviti alle riunioni generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="16220-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="16220-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16220-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="16220-140">Aggiunge il logo dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="16220-141">È possibile specificare l'URL di un'immagine GIF o JPG.</span><span class="sxs-lookup"><span data-stu-id="16220-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="16220-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="16220-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16220-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="16220-144">Aggiunge l'URL della guida o del supporto dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="16220-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="16220-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16220-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="16220-147">Aggiunge testo legale o testo di dichiarazione di non responsabilità a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="16220-148">È possibile specificare l'URL del percorso del testo.</span><span class="sxs-lookup"><span data-stu-id="16220-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="16220-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="16220-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="16220-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="16220-151">Aggiunge un piè di pagina personalizzato a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="16220-152">È possibile specificare l'URL del percorso del testo di piè di pagina personalizzato.</span><span class="sxs-lookup"><span data-stu-id="16220-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="16220-153">Parametri di gestione client deprecati</span><span class="sxs-lookup"><span data-stu-id="16220-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16220-154">Parametro</span><span class="sxs-lookup"><span data-stu-id="16220-154">Parameter</span></span></th>
<th><span data-ttu-id="16220-155">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="16220-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="16220-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16220-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16220-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="16220-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="16220-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-159">Questo parametro è obsoleto per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="16220-160">Quando viene utilizzato insieme a EnableEnterpriseCustomizedHelp, questo parametro ha consentito a un'organizzazione di specificare un URL in modo che, quando gli utenti hanno fatto clic sul menu della Guida in Lync, la guida personalizzata verrebbe visualizzata.</span><span class="sxs-lookup"><span data-stu-id="16220-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="16220-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="16220-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-163">Questo parametro è obsoleto per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="16220-164">Quando viene utilizzato insieme a CustomizedHelpUrl, questo parametro consente alle organizzazioni di visualizzare la guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="16220-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="16220-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="16220-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-167">Il parametro EnableSQMData del cmdlet Set-CSClientPolicy è stato rimosso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="16220-168">È invece possibile utilizzare l'impostazione condivisa di Criteri di gruppo per i dati SQM (Software Quality Management) per determinare l'interfaccia utente per l'opzione per l'Analisi utilizzo software nella pagina delle opzioni generali del client Lync:</span><span class="sxs-lookup"><span data-stu-id="16220-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="16220-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="16220-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="16220-170">Valori</span><span class="sxs-lookup"><span data-stu-id="16220-170">Values:</span></span></p>
<p><span data-ttu-id="16220-171">1 = la casella di controllo viene visualizzata e selezionata (l'utente può deselezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="16220-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="16220-172">0 = la casella di controllo viene disattivata e disabilitata (l'utente non può modificare l'impostazione).</span><span class="sxs-lookup"><span data-stu-id="16220-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="16220-173">Null = il valore è determinato dal programma di installazione di Office e la casella di controllo viene visualizzata in modo che gli utenti possano impostarla come desiderato.</span><span class="sxs-lookup"><span data-stu-id="16220-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="16220-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="16220-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-176">Questo parametro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="16220-176">This parameter has been removed.</span></span> <span data-ttu-id="16220-177">Invece, quando si distribuisce Lync Server 2013 e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="16220-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="16220-178">Questo significa che tutti i contatti di un utente vengono mantenuti in Exchange e sono disponibili in Lync, Outlook e Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="16220-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="16220-179">È possibile utilizzare il cmdlet Set-CsUserServicesPolicy per personalizzare gli utenti per i quali è disponibile l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="16220-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="16220-180">È possibile abilitare gli utenti globalmente, in base al sito, al tenant oppure a persone singole o gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="16220-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="16220-181">Per ulteriori informazioni, vedere <a href="lync-server-2013-enable-users-for-unified-contact-store.md">abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="16220-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16220-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="16220-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="16220-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-184">Questo parametro non viene utilizzato da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="16220-185">Nelle versioni precedenti questo parametro specifica la frequenza con cui il client recupera i dati MAPI dalle cartelle pubbliche di Exchange.</span><span class="sxs-lookup"><span data-stu-id="16220-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16220-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="16220-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="16220-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="16220-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="16220-188">Questo parametro è obsoleto in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="16220-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

