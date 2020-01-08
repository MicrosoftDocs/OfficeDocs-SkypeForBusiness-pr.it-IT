---
title: 'Lync Server 2013: impostazioni nuove e modificate per Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="8d1b7-102">Impostazioni nuove e modificate per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8d1b7-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d1b7-103">_**Argomento Ultima modifica:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="8d1b7-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="8d1b7-104">Questo argomento illustra le modifiche apportate ai cmdlet di Lync Server Management Shell che si ricollegano direttamente alla gestione client.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="8d1b7-105">Lync Server 2013 introduce diversi nuovi parametri e depreca i parametri per le caratteristiche che possono essere configurate con altri strumenti.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="8d1b7-106">Nuovi parametri di gestione client</span><span class="sxs-lookup"><span data-stu-id="8d1b7-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d1b7-107">Nuovo</span><span class="sxs-lookup"><span data-stu-id="8d1b7-107">New</span></span></th>
<th><span data-ttu-id="8d1b7-108">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d1b7-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="8d1b7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d1b7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="8d1b7-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-112">Quando è impostato su true, l'analisi del software verrà abilitata in Lync. Quando è impostato su false, la traccia del software verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="8d1b7-113">L'analisi del software consiste nel tenere traccia dettagliata di tutto ciò che fa un programma (incluse le chiamate API di rilevamento).</span><span class="sxs-lookup"><span data-stu-id="8d1b7-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="8d1b7-114">La traccia è in gran parte utile per gli sviluppatori e per il personale di supporto dell'applicazione. Questa impostazione è equivalente all'impostazione &quot;di criteri di gruppo Communications Server 2007 R2 attiva l'analisi per Communicator. &quot; Le impostazioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d1b7-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8d1b7-115">Off = la traccia è disabilitata e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="8d1b7-116">Light = viene eseguita la traccia minima e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="8d1b7-117">On = la traccia dettagliata viene eseguita e l'utente non può modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="8d1b7-118">Per impostazione predefinita, TracingLevel è impostato su un valore null.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="8d1b7-119">Ciò significa che viene eseguita la traccia minima, ma l'utente può abilitare o disabilitare questa traccia minima.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="8d1b7-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-122">Se impostato su true ($True) consente la separazione dei flussi audio e video dall'altro traffico di rete, a sua volta, questo consente ai dispositivi client di eseguire la codifica e decodifica di audio e video localmente.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="8d1b7-123">Il reindirizzamento multimediale genera in genere un uso più basso della larghezza di banda, una scalabilità più elevata del server e un'esperienza utente più ottimale rispetto alle tecniche simili, ad esempio i servizi remoti o la compressione dei codec.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="8d1b7-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d1b7-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-126">Quando è impostato su true, tutte le riunioni Lync vengono &quot;gestite come riunioni di grandi dimensioni. &quot; Con una riunione di grandi dimensioni, le restrizioni vengono inserite nel numero di notifiche inviate ai partecipanti, oltre alle dimensioni del roster delle riunioni trasmesse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="8d1b7-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d1b7-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-129">Quando impostato su true ($True) gli utenti non potranno aggiungere annotazioni alle diapositive di PowerPoint usate in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="8d1b7-130">Tuttavia, a seconda del valore della proprietà AllowAnnotations, gli utenti avranno comunque accesso ad altre caratteristiche di lavagna.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="8d1b7-131">Il valore predefinito è false, ovvero le annotazioni di PowerPoint sono consentite.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="8d1b7-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d1b7-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-134">Quando è impostato su true (il valore predefinito) i blocchi appunti di OneNote aperti collegati alla conferenza verranno aggiornati automaticamente con informazioni come i partecipanti alla conferenza e i dettagli sul contenuto condiviso durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="8d1b7-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d1b7-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-137">Usato insieme agli altri nuovi parametri di CsMeetingConfiguration per personalizzare gli inviti alle riunioni generati dal componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="8d1b7-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d1b7-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-140">Aggiunge il logo dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d1b7-141">Devi specificare l'URL di un'immagine GIF o JPG.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="8d1b7-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d1b7-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-144">Aggiunge l'URL della guida o del supporto dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="8d1b7-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d1b7-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-147">Aggiunge testo giuridico o Disclaimer a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d1b7-148">Devi specificare l'URL per la posizione del testo.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="8d1b7-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d1b7-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-151">Aggiunge un piè di pagina personalizzato a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d1b7-152">Devi specificare l'URL per la posizione del testo del piè di pagina personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="8d1b7-153">Parametri di gestione client deprecati</span><span class="sxs-lookup"><span data-stu-id="8d1b7-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d1b7-154">Parametro</span><span class="sxs-lookup"><span data-stu-id="8d1b7-154">Parameter</span></span></th>
<th><span data-ttu-id="8d1b7-155">Cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d1b7-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="8d1b7-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d1b7-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="8d1b7-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-159">Questo parametro è stato deprecato per l'uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="8d1b7-160">Quando viene usato in combinazione con EnableEnterpriseCustomizedHelp, questo parametro ha consentito a un'organizzazione di specificare un URL in modo che quando gli utenti hanno fatto clic sul menu della Guida in Lync, verrebbe visualizzata una guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="8d1b7-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-163">Questo parametro è stato deprecato per l'uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="8d1b7-164">Se usato in combinazione con CustomizedHelpUrl, questo parametro consente alle organizzazioni di visualizzare la guida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="8d1b7-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-167">Il parametro EnableSQMData del cmdlet Set-CSClientPolicy è stato rimosso in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="8d1b7-168">È invece possibile usare l'impostazione di criteri di gruppo condivisi per i dati di gestione della qualità software (SQM) per determinare l'interfaccia utente per l'opzione Analisi utilizzo clienti nella pagina Opzioni generali client di Lync:</span><span class="sxs-lookup"><span data-stu-id="8d1b7-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="8d1b7-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="8d1b7-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="8d1b7-170">Valori</span><span class="sxs-lookup"><span data-stu-id="8d1b7-170">Values:</span></span></p>
<p><span data-ttu-id="8d1b7-171">1 = Visualizza e selezionare la casella di controllo (l'utente può deselezionare la casella di controllo)</span><span class="sxs-lookup"><span data-stu-id="8d1b7-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="8d1b7-172">0 = disattiva e Disabilita la casella di controllo (l'utente non può eseguire l'override)</span><span class="sxs-lookup"><span data-stu-id="8d1b7-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="8d1b7-173">Null = il valore è determinato dalla configurazione di Office e la casella di controllo viene visualizzata per consentire agli utenti di impostare la scelta</span><span class="sxs-lookup"><span data-stu-id="8d1b7-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="8d1b7-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-176">Questo parametro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-176">This parameter has been removed.</span></span> <span data-ttu-id="8d1b7-177">Quando si distribuisce Lync Server 2013 e si pubblica la topologia, viene invece abilitato l'archivio contatti unificato per tutti gli utenti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="8d1b7-178">Ciò significa che tutti i contatti di un utente vengono mantenuti in Exchange e sono disponibili in Lync, Outlook e Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="8d1b7-179">Puoi usare il cmdlet Set-CsUserServicesPolicy per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="8d1b7-180">Puoi abilitare gli utenti a livello globale, per sito, per tenant o per singoli o gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="8d1b7-181">Per informazioni dettagliate, vedere <a href="lync-server-2013-enable-users-for-unified-contact-store.md">abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d1b7-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="8d1b7-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-184">Questo parametro non viene usato da Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="8d1b7-185">Nelle versioni precedenti questo parametro specifica la frequenza con cui il client ha recuperato i dati MAPI dalle cartelle pubbliche di Exchange</span><span class="sxs-lookup"><span data-stu-id="8d1b7-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d1b7-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="8d1b7-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d1b7-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d1b7-188">Questo parametro è deprecato in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b7-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

