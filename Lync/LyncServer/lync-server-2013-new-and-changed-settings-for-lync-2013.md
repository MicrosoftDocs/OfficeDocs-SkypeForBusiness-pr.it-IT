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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Impostazioni nuove e modificate per Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-05_

Questo argomento illustra le modifiche apportate ai cmdlet di Lync Server Management Shell che si ricollegano direttamente alla gestione client. Lync Server 2013 introduce diversi nuovi parametri e depreca i parametri per le caratteristiche che possono essere configurate con altri strumenti.

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
<th>Nuovo</th>
<th>Cmdlet di Lync Server Management Shell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Quando è impostato su true, l'analisi del software verrà abilitata in Lync. Quando è impostato su false, la traccia del software verrà disabilitata. L'analisi del software consiste nel tenere traccia dettagliata di tutto ciò che fa un programma (incluse le chiamate API di rilevamento). La traccia è in gran parte utile per gli sviluppatori e per il personale di supporto dell'applicazione. Questa impostazione è equivalente all'impostazione &quot;di criteri di gruppo Communications Server 2007 R2 attiva l'analisi per Communicator. &quot; Le impostazioni sono le seguenti:</p>
<ul>
<li><p>Off = la traccia è disabilitata e l'utente non può modificare questa impostazione.</p></li>
<li><p>Light = viene eseguita la traccia minima e l'utente non può modificare questa impostazione.</p></li>
<li><p>On = la traccia dettagliata viene eseguita e l'utente non può modificare questa impostazione.</p></li>
</ul>
<p>Per impostazione predefinita, TracingLevel è impostato su un valore null. Ciò significa che viene eseguita la traccia minima, ma l'utente può abilitare o disabilitare questa traccia minima.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Se impostato su true ($True) consente la separazione dei flussi audio e video dall'altro traffico di rete, a sua volta, questo consente ai dispositivi client di eseguire la codifica e decodifica di audio e video localmente. Il reindirizzamento multimediale genera in genere un uso più basso della larghezza di banda, una scalabilità più elevata del server e un'esperienza utente più ottimale rispetto alle tecniche simili, ad esempio i servizi remoti o la compressione dei codec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando è impostato su true, tutte le riunioni Lync vengono &quot;gestite come riunioni di grandi dimensioni. &quot; Con una riunione di grandi dimensioni, le restrizioni vengono inserite nel numero di notifiche inviate ai partecipanti, oltre alle dimensioni del roster delle riunioni trasmesse per impostazione predefinita.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando impostato su true ($True) gli utenti non potranno aggiungere annotazioni alle diapositive di PowerPoint usate in una conferenza. Tuttavia, a seconda del valore della proprietà AllowAnnotations, gli utenti avranno comunque accesso ad altre caratteristiche di lavagna. Il valore predefinito è false, ovvero le annotazioni di PowerPoint sono consentite.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quando è impostato su true (il valore predefinito) i blocchi appunti di OneNote aperti collegati alla conferenza verranno aggiornati automaticamente con informazioni come i partecipanti alla conferenza e i dettagli sul contenuto condiviso durante la conferenza.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Usato insieme agli altri nuovi parametri di CsMeetingConfiguration per personalizzare gli inviti alle riunioni generati dal componente aggiuntivo riunione online per Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge il logo dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013. Devi specificare l'URL di un'immagine GIF o JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge l'URL della guida o del supporto dell'organizzazione a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge testo giuridico o Disclaimer a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013. Devi specificare l'URL per la posizione del testo.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Aggiunge un piè di pagina personalizzato a tutti gli inviti generati dal componente aggiuntivo riunione online per Lync 2013. Devi specificare l'URL per la posizione del testo del piè di pagina personalizzato.</p></td>
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
<td><p>Questo parametro è stato deprecato per l'uso con Lync Server 2013. Quando viene usato in combinazione con EnableEnterpriseCustomizedHelp, questo parametro ha consentito a un'organizzazione di specificare un URL in modo che quando gli utenti hanno fatto clic sul menu della Guida in Lync, verrebbe visualizzata una guida personalizzata.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è stato deprecato per l'uso con Lync Server 2013. Se usato in combinazione con CustomizedHelpUrl, questo parametro consente alle organizzazioni di visualizzare la guida personalizzata.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Il parametro EnableSQMData del cmdlet Set-CSClientPolicy è stato rimosso in Lync Server 2013. È invece possibile usare l'impostazione di criteri di gruppo condivisi per i dati di gestione della qualità software (SQM) per determinare l'interfaccia utente per l'opzione Analisi utilizzo clienti nella pagina Opzioni generali client di Lync:</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valori</p>
<p>1 = Visualizza e selezionare la casella di controllo (l'utente può deselezionare la casella di controllo)</p>
<p>0 = disattiva e Disabilita la casella di controllo (l'utente non può eseguire l'override)</p>
<p>Null = il valore è determinato dalla configurazione di Office e la casella di controllo viene visualizzata per consentire agli utenti di impostare la scelta</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è stato rimosso. Quando si distribuisce Lync Server 2013 e si pubblica la topologia, viene invece abilitato l'archivio contatti unificato per tutti gli utenti per impostazione predefinita. Ciò significa che tutti i contatti di un utente vengono mantenuti in Exchange e sono disponibili in Lync, Outlook e Outlook Web Access. Puoi usare il cmdlet Set-CsUserServicesPolicy per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile. Puoi abilitare gli utenti a livello globale, per sito, per tenant o per singoli o gruppi di persone. Per informazioni dettagliate, vedere <a href="lync-server-2013-enable-users-for-unified-contact-store.md">abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro non viene usato da Lync 2013. Nelle versioni precedenti questo parametro specifica la frequenza con cui il client ha recuperato i dati MAPI dalle cartelle pubbliche di Exchange</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Questo parametro è deprecato in Lync 2013.</p></td>
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

