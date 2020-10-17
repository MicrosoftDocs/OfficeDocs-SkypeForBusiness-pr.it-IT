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
# <a name="new-and-changed-settings-for-lync-2013"></a>Impostazioni nuove e modificate per Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-05_

In questo argomento vengono illustrate le modifiche apportate ai cmdlet di Lync Server Management Shell correlati direttamente alla gestione client. Lync Server 2013 introduce diversi nuovi parametri e depreca i parametri per le funzionalità che possono essere configurate con altri metodi.

<div>

## <a name="new-client-management-parameters"></a>Nuovi parametri di gestione client


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nuova</th>
<th>Cmdlet di Lync Server Management Shell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Se impostato su true, l'analisi del software verrà abilitata in Lync. Se impostato su false, l'analisi del software verrà disabilitata. L'analisi del software implica la conservazione di una registrazione dettagliata di tutto ciò che un programma esegue (incluse le chiamate API di rilevamento). L'analisi è utile principalmente per gli sviluppatori e per il personale di supporto dell'applicazione. Questa impostazione equivale all'impostazione di criteri di gruppo di Communications Server 2007 R2 &quot; attiva l'analisi per Communicator. &quot; Di seguito sono riportate le impostazioni seguenti:</p>
<ul>
<li><p>Off = la traccia è disabilita e l'utente non può modificare questa impostazione.</p></li>
<li><p>Light = viene eseguita la traccia con livello minimo e l'utente non può modificare questa impostazione.</p></li>
<li><p>On = viene eseguita la traccia con livello dettagliato e l'utente non può modificare questa impostazione.</p></li>
</ul>
<p>Per impostazione predefinita, TracingLevel è impostato su un valore Null. Questo significa che verrà eseguita la traccia con livello minimo, ma che l'utente potrà abilitare o disabilitare questa traccia minima.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Se impostato su True ($True), consente la separazione dei flussi audio e video dal resto del traffico di rete. I dispositivi client possono quindi eseguire la codifica e decodifica dei dati audio e video localmente. Il reindirizzamento dei dati multimediali in genere comporta un minore utilizzo della larghezza di banda, una maggiore scalabilità dei server e un'esperienza utente più ottimizzata rispetto a tecniche simili, come la gestione remota dei dispositivi o la compressione dei codec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Se impostato su true, tutte le riunioni di Lync vengono trattate come &quot; riunioni di grandi dimensioni. &quot; Con una riunione di grandi dimensioni, vengono applicate le restrizioni sul numero di notifiche inviate ai partecipanti, oltre alle dimensioni dell'elenco di riunioni trasmesso per impostazione predefinita.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Se impostato su True ($True), gli utenti non potranno aggiungere annotazioni alle diapositive di PowerPoint utilizzate in una conferenza. Tuttavia, a seconda del valore della proprietà AllowAnnotations, gli utenti potranno comunque accedere ad altre funzionalità della lavagna. Il valore predefinito è False, pertanto le annotazioni di PowerPoint sono consentite.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Se impostato su True (valore predefinito), tutti gli eventuali blocchi appunti di OneNote aperti e collegati alla conferenza verranno aggiornati automaticamente con informazioni come i partecipanti alla conferenza e i dettagli sul contenuto condiviso durante la conferenza.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Utilizzato insieme agli altri nuovi parametri di CsMeetingConfiguration per personalizzare gli inviti alle riunioni generati dal componente aggiuntivo per riunioni online per Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge il logo dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013. È possibile specificare l'URL di un'immagine GIF o JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge l'URL della guida o del supporto dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge testo legale o testo di dichiarazione di non responsabilità a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013. È possibile specificare l'URL del percorso del testo.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge un piè di pagina personalizzato a tutti gli inviti generati dal componente aggiuntivo per riunioni online per Lync 2013. È possibile specificare l'URL del percorso del testo di piè di pagina personalizzato.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Parametri di gestione client deprecati


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro</th>
<th>Cmdlet di Lync Server Management Shell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è obsoleto per l'utilizzo con Lync Server 2013. Quando viene utilizzato insieme a EnableEnterpriseCustomizedHelp, questo parametro ha consentito a un'organizzazione di specificare un URL in modo che, quando gli utenti hanno fatto clic sul menu della Guida in Lync, la guida personalizzata verrebbe visualizzata.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è obsoleto per l'utilizzo con Lync Server 2013. Quando viene utilizzato insieme a CustomizedHelpUrl, questo parametro consente alle organizzazioni di visualizzare la guida personalizzata.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Il parametro EnableSQMData del cmdlet Set-CSClientPolicy è stato rimosso in Lync Server 2013. È invece possibile utilizzare l'impostazione condivisa di Criteri di gruppo per i dati SQM (Software Quality Management) per determinare l'interfaccia utente per l'opzione per l'Analisi utilizzo software nella pagina delle opzioni generali del client Lync:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valori</p>
<p>1 = la casella di controllo viene visualizzata e selezionata (l'utente può deselezionare la casella di controllo).</p>
<p>0 = la casella di controllo viene disattivata e disabilitata (l'utente non può modificare l'impostazione).</p>
<p>Null = il valore è determinato dal programma di installazione di Office e la casella di controllo viene visualizzata in modo che gli utenti possano impostarla come desiderato.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è stato rimosso. Invece, quando si distribuisce Lync Server 2013 e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita. Questo significa che tutti i contatti di un utente vengono mantenuti in Exchange e sono disponibili in Lync, Outlook e Outlook Web Access. È possibile utilizzare il cmdlet Set-CsUserServicesPolicy per personalizzare gli utenti per i quali è disponibile l'archivio contatti unificato. È possibile abilitare gli utenti globalmente, in base al sito, al tenant oppure a persone singole o gruppi di persone. Per ulteriori informazioni, vedere <a href="lync-server-2013-enable-users-for-unified-contact-store.md">abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro non viene utilizzato da Lync 2013. Nelle versioni precedenti questo parametro specifica la frequenza con cui il client recupera i dati MAPI dalle cartelle pubbliche di Exchange.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è obsoleto in Lync 2013.</p></td>
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

