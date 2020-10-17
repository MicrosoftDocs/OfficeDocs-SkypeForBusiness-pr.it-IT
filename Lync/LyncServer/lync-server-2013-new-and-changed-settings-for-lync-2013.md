---
title: 'Lync Server 2013: impostazioni nuove e modificate per Lync 2013'
description: 'Lync Server 2013: impostazioni nuove e modificate per Lync 2013.'
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
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561392"
---
# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="e9a14-103">Impostazioni nuove e modificate per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e9a14-103">New and changed settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9a14-104">_**Ultimo argomento modificato:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="e9a14-104">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="e9a14-105">In questo argomento vengono illustrate le modifiche apportate ai cmdlet di Lync Server Management Shell correlati direttamente alla gestione client.</span><span class="sxs-lookup"><span data-stu-id="e9a14-105">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="e9a14-106">Lync Server 2013 introduce diversi nuovi parametri e depreca i parametri per le funzionalità che possono essere configurate con altri metodi.</span><span class="sxs-lookup"><span data-stu-id="e9a14-106">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="e9a14-107">Nuovi parametri di gestione client</span><span class="sxs-lookup"><span data-stu-id="e9a14-107">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9a14-108">Nuova</span><span class="sxs-lookup"><span data-stu-id="e9a14-108">New</span></span></th>
<th><span data-ttu-id="e9a14-109">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e9a14-109">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="e9a14-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9a14-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-111">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="e9a14-111">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="e9a14-112">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-112">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-113">Se impostato su true, l'analisi del software verrà abilitata in Lync. Se impostato su false, l'analisi del software verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e9a14-113">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="e9a14-114">L'analisi del software implica la conservazione di una registrazione dettagliata di tutto ciò che un programma esegue (incluse le chiamate API di rilevamento).</span><span class="sxs-lookup"><span data-stu-id="e9a14-114">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="e9a14-115">L'analisi è utile principalmente per gli sviluppatori e per il personale di supporto dell'applicazione. Questa impostazione equivale all'impostazione di criteri di gruppo di Communications Server 2007 R2 &quot; attiva l'analisi per Communicator. &quot; Di seguito sono riportate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9a14-115">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e9a14-116">Off = la traccia è disabilita e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="e9a14-116">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="e9a14-117">Light = viene eseguita la traccia con livello minimo e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="e9a14-117">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="e9a14-118">On = viene eseguita la traccia con livello dettagliato e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="e9a14-118">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="e9a14-p103">Per impostazione predefinita, TracingLevel è impostato su un valore Null. Questo significa che verrà eseguita la traccia con livello minimo, ma che l'utente potrà abilitare o disabilitare questa traccia minima.</span><span class="sxs-lookup"><span data-stu-id="e9a14-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-121">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="e9a14-121">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="e9a14-122">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-122">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-p104">Se impostato su True ($True), consente la separazione dei flussi audio e video dal resto del traffico di rete. I dispositivi client possono quindi eseguire la codifica e decodifica dei dati audio e video localmente. Il reindirizzamento dei dati multimediali in genere comporta un minore utilizzo della larghezza di banda, una maggiore scalabilità dei server e un'esperienza utente più ottimizzata rispetto a tecniche simili, come la gestione remota dei dispositivi o la compressione dei codec.</span><span class="sxs-lookup"><span data-stu-id="e9a14-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-125">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="e9a14-125">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="e9a14-126">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="e9a14-126">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="e9a14-127">Se impostato su true, tutte le riunioni di Lync vengono trattate come &quot; riunioni di grandi dimensioni. &quot; Con una riunione di grandi dimensioni, vengono applicate le restrizioni sul numero di notifiche inviate ai partecipanti, oltre alle dimensioni dell'elenco di riunioni trasmesso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e9a14-127">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-128">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="e9a14-128">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="e9a14-129">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="e9a14-129">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="e9a14-p105">Se impostato su True ($True), gli utenti non potranno aggiungere annotazioni alle diapositive di PowerPoint utilizzate in una conferenza. Tuttavia, a seconda del valore della proprietà AllowAnnotations, gli utenti potranno comunque accedere ad altre funzionalità della lavagna. Il valore predefinito è False, pertanto le annotazioni di PowerPoint sono consentite.</span><span class="sxs-lookup"><span data-stu-id="e9a14-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-133">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="e9a14-133">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="e9a14-134">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="e9a14-134">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="e9a14-135">Se impostato su True (valore predefinito), tutti gli eventuali blocchi appunti di OneNote aperti e collegati alla conferenza verranno aggiornati automaticamente con informazioni come i partecipanti alla conferenza e i dettagli sul contenuto condiviso durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e9a14-135">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-136">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="e9a14-136">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="e9a14-137">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a14-137">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="e9a14-138">Utilizzato insieme agli altri nuovi parametri di CsMeetingConfiguration per personalizzare gli inviti alle riunioni generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-138">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-139">LogoURL</span><span class="sxs-lookup"><span data-stu-id="e9a14-139">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="e9a14-140">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a14-140">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="e9a14-141">Aggiunge il logo dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-141">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="e9a14-142">È possibile specificare l'URL di un'immagine GIF o JPG.</span><span class="sxs-lookup"><span data-stu-id="e9a14-142">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-143">HelpURL</span><span class="sxs-lookup"><span data-stu-id="e9a14-143">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="e9a14-144">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a14-144">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="e9a14-145">Aggiunge l'URL della guida o del supporto dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-145">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-146">LegalURL</span><span class="sxs-lookup"><span data-stu-id="e9a14-146">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="e9a14-147">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a14-147">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="e9a14-148">Aggiunge testo legale o testo di dichiarazione di non responsabilità a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-148">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="e9a14-149">È possibile specificare l'URL del percorso del testo.</span><span class="sxs-lookup"><span data-stu-id="e9a14-149">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-150">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="e9a14-150">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="e9a14-151">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a14-151">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="e9a14-152">Aggiunge un piè di pagina personalizzato a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-152">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="e9a14-153">È possibile specificare l'URL del percorso del testo di piè di pagina personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e9a14-153">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="e9a14-154">Parametri di gestione client deprecati</span><span class="sxs-lookup"><span data-stu-id="e9a14-154">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9a14-155">Parametro</span><span class="sxs-lookup"><span data-stu-id="e9a14-155">Parameter</span></span></th>
<th><span data-ttu-id="e9a14-156">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e9a14-156">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="e9a14-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9a14-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-158">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="e9a14-158">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="e9a14-159">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-159">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-160">Questo parametro è obsoleto per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-160">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="e9a14-161">Quando viene utilizzato insieme a EnableEnterpriseCustomizedHelp, questo parametro ha consentito a un'organizzazione di specificare un URL in modo che, quando gli utenti hanno fatto clic sul menu della Guida in Lync, la guida personalizzata verrebbe visualizzata.</span><span class="sxs-lookup"><span data-stu-id="e9a14-161">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-162">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="e9a14-162">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="e9a14-163">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-163">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-164">Questo parametro è obsoleto per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-164">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="e9a14-165">Quando viene utilizzato insieme a CustomizedHelpUrl, questo parametro consente alle organizzazioni di visualizzare la guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e9a14-165">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-166">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="e9a14-166">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="e9a14-167">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-167">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-168">Il parametro EnableSQMData del cmdlet Set-CSClientPolicy è stato rimosso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-168">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="e9a14-169">È invece possibile utilizzare l'impostazione condivisa di Criteri di gruppo per i dati SQM (Software Quality Management) per determinare l'interfaccia utente per l'opzione per l'Analisi utilizzo software nella pagina delle opzioni generali del client Lync:</span><span class="sxs-lookup"><span data-stu-id="e9a14-169">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="e9a14-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="e9a14-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="e9a14-171">Valori</span><span class="sxs-lookup"><span data-stu-id="e9a14-171">Values:</span></span></p>
<p><span data-ttu-id="e9a14-172">1 = la casella di controllo viene visualizzata e selezionata (l'utente può deselezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="e9a14-172">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="e9a14-173">0 = la casella di controllo viene disattivata e disabilitata (l'utente non può modificare l'impostazione).</span><span class="sxs-lookup"><span data-stu-id="e9a14-173">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="e9a14-174">Null = il valore è determinato dal programma di installazione di Office e la casella di controllo viene visualizzata in modo che gli utenti possano impostarla come desiderato.</span><span class="sxs-lookup"><span data-stu-id="e9a14-174">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-175">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="e9a14-175">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="e9a14-176">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-176">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-177">Questo parametro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="e9a14-177">This parameter has been removed.</span></span> <span data-ttu-id="e9a14-178">Invece, quando si distribuisce Lync Server 2013 e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e9a14-178">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="e9a14-179">Questo significa che tutti i contatti di un utente vengono mantenuti in Exchange e sono disponibili in Lync, Outlook e Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="e9a14-179">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="e9a14-180">È possibile utilizzare il cmdlet Set-CsUserServicesPolicy per personalizzare gli utenti per i quali è disponibile l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e9a14-180">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="e9a14-181">È possibile abilitare gli utenti globalmente, in base al sito, al tenant oppure a persone singole o gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="e9a14-181">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="e9a14-182">Per ulteriori informazioni, vedere <a href="lync-server-2013-enable-users-for-unified-contact-store.md">abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e9a14-182">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9a14-183">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="e9a14-183">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="e9a14-184">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-184">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-185">Questo parametro non viene utilizzato da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-185">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="e9a14-186">Nelle versioni precedenti questo parametro specifica la frequenza con cui il client recupera i dati MAPI dalle cartelle pubbliche di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9a14-186">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a14-187">DisableICE</span><span class="sxs-lookup"><span data-stu-id="e9a14-187">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="e9a14-188">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="e9a14-188">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="e9a14-189">Questo parametro è obsoleto in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e9a14-189">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

