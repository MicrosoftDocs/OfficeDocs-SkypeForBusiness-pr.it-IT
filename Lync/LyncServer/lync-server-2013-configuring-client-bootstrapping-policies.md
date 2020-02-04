---
title: 'Lync Server 2013: configurazione dei criteri di avvio del client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configurazione dei criteri di avvio del client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti usati per gestire i criteri di gruppo. Incluso nel modello di amministrazione di criteri di gruppo di Office sono i modelli amministrativi di Lync 2013. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basate sul Registro di sistema configurate per gli oggetti Criteri di gruppo nel dominio. I file ADML sono complementi specifici della lingua per i file ADMX. Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office. Per altre informazioni, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di Office <http://go.microsoft.com/fwlink/p/?linkid=267516>2013 all'indirizzo.

Per Lync 2013, sono disponibili diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti accedino al server per la prima volta. Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve usare fino al completamento dell'accesso. È possibile usare criteri di gruppo per stabilire queste impostazioni nei registri computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server. Nella tabella seguente sono elencate le impostazioni dei criteri di gruppo disponibili per Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Impostazioni di criteri di gruppo per Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione di criteri di gruppo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Specificare il server<br />
ConfigurationMode</p></td>
<td><p>Specifica in che modo Lync 2013 identifica il trasporto e il server da usare durante l'accesso. In questa impostazione è necessario specificare quanto segue:</p>
<ul>
<li><p>ServerAddressExternal: specifica il nome del server o l'indirizzo IP usato dai client e dai contatti federati quando ci si connette dall'esterno del firewall esterno.</p></li>
<li><p>ServerAddressInternal: specifica il nome del server o l'indirizzo IP usato quando i client si connettono dall'interno del firewall dell'organizzazione.</p></li>
<li><p>Transport: specifica TCP (Transmission Control Protocol) o Transport Layer Security (TLS).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versioni del server aggiuntive supportate<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Specifica un elenco di nomi di versione del server separati da punti e virgola a cui Lync Server 2013 accederà, oltre alle versioni del server supportate per impostazione predefinita.</p></td>
</tr>
<tr class="odd">
<td><p>Disabilitare il caricamento automatico dei log di errore di accesso (DisableAutomaticSendTracing)</p></td>
<td><p>Carica automaticamente i registri di errore di accesso in Lync Server per l'analisi. Nessun log viene caricato automaticamente se l'accesso è riuscito. Se questo criterio non è configurato, si verifica quanto segue:</p>
<dl>
<dt><span></span></dt>
<dd><p>Per gli utenti di Lync Online: i registri di errore di accesso vengono caricati automaticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Per gli utenti locali di Lync: la finestra di dialogo di conferma viene visualizzata all'utente prima del caricamento.</p>
</dd>
</dl>
<p>Quando questa impostazione è disabilitata, i log di accesso vengono caricati automaticamente nel server Lync per gli utenti di Lync locale e Lync Online. Quando questa impostazione è abilitata, i log di accesso non vengono mai caricati automaticamente.</p></td>
</tr>
<tr class="even">
<td><p>Disabilitare il fallback HTTP per la connessione SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impedisce a Lync Server di provare a connettersi al server tramite HTTP, se TLS o TCP non sono disponibili. Per impostazione predefinita, Lync cerca prima di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto riesce, Lync prova a connettersi tramite HTTP. Usare questo criterio per disabilitare il tentativo di connessione HTTP di fallback.</p></td>
</tr>
<tr class="odd">
<td><p>Richiedere le credenziali di accesso<br />
DisableNTCredentials</p></td>
<td><p>Richiede all'utente di specificare le credenziali di accesso per Lync anziché utilizzare automaticamente le credenziali di Windows durante l'accesso a un server SIP.</p></td>
</tr>
<tr class="even">
<td><p>Disabilitare il controllo della versione del server<br />
(DisableServerCheck)</p></td>
<td><p>Se si imposta questo criterio su 1, viene impedito a Lync di verificare il nome e la versione del server prima dell'accesso. Per impostazione predefinita, Lync effettua questi controlli prima di eseguire l'accesso.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'uso di bit per scaricare i file del servizio Rubrica<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Consente a Lync di usare il servizio di trasferimento intelligente in background (BITS) per scaricare i file dei servizi Rubrica.</p></td>
</tr>
<tr class="even">
<td><p>Configurare la modalità di sicurezza SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Consente a Lync di inviare e ricevere messaggi istantanei in modo più sicuro. Questo criterio non ha alcun effetto sui servizi Windows .NET o Microsoft Exchange Server.</p>
<p>Se non si configura questa impostazione, Lync può usare qualsiasi trasporto. Ma se non usa TLS e se il server autentica gli utenti, Lync deve usare l'autenticazione NTLM o Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Scarica il ritardo iniziale della Rubrica globale<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Specifica il periodo di tempo prima che si verifichi il download dell'elenco indirizzi globale (GAL). Il valore predefinito è 60 minuti, quindi il server ritarda il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.</p></td>
</tr>
<tr class="even">
<td><p>Evitare che gli utenti eseguano Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impedisce agli utenti di eseguire Lync. È possibile configurare questa impostazione per i criteri in configurazione computer e configurazione utente, ma l'impostazione dei criteri in configurazione computer ha la precedenza.</p></td>
</tr>
<tr class="odd">
<td><p>Consentire l'archiviazione delle password degli utenti<br />
(SavePassword)</p></td>
<td><p>Consente a Lync di archiviare le password.</p></td>
</tr>
<tr class="even">
<td><p>Configurare la modalità di compressione SIP<br />
SipCompression</p></td>
<td><p>Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tieni presente che l'impostazione di questo criterio può causare un aumento dell'ora di accesso.</p></td>
</tr>
<tr class="odd">
<td><p>Elenco domini attendibili<br />
TrustModelData</p></td>
<td><p>Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.</p></td>
</tr>
</tbody>
</table>


I criteri configurati nel server hanno la precedenza sulle impostazioni dei criteri di gruppo e le opzioni client configurate dall'utente. Nella tabella seguente viene riepilogato l'ordine in cui le impostazioni hanno la precedenza quando si verifica un conflitto.

### <a name="group-policy-precedence"></a>Precedenza dei criteri di gruppo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedenza</th>
<th>Posizione o metodo di impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Provisioning in-band di Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Finestra di dialogo Lync-Opzioni in Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Per definire le impostazioni dei criteri di gruppo usando i file dei modelli amministrativi di Lync 2013

1.  Creare una cartella a livello radice per contenere tutti i file ADMX indipendenti dalla lingua. Ad esempio, crea la cartella radice per l'archivio centrale nel controller di dominio in questa posizione:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > In questa procedura si presuppone che si vogliano gestire più computer nel dominio. In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario. In questo modo viene fornito un percorso di archiviazione centralizzato replicato per i modelli amministrativi del dominio.

    
    </div>

2.  Creare una sottocartella per ogni lingua che verrà usata. Queste sottocartelle conterranno i file di risorse ADML specifici della lingua. Ad esempio, creare una sottocartella per gli Stati Uniti in inglese (EN-US) in questa posizione:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

