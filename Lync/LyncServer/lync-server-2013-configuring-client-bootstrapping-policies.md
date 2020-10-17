---
title: 'Lync Server 2013: configurazione dei criteri di avvio automatico dei client'
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
ms.openlocfilehash: 826f732f25996a9f8fcbd708f7e76157a5753a01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512773"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configurazione dei criteri di avvio automatico dei client in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti che è possibile utilizzare per gestire i criteri di gruppo. Con il modello amministrativo di criteri di gruppo di Office sono inclusi i modelli amministrativi di Lync 2013. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basati sul Registro di sistema che vengono configurate per gli oggetti Criteri di gruppo nel dominio. I file ADML sono complementi specifici della lingua per i file ADMX. Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office. Per ulteriori informazioni, vedere "file dei modelli amministrativi di Office 2013 (ADMX, ADML)" nella documentazione di Office 2013 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=267516> .

Per Lync 2013, sono disponibili diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti eseguano l'accesso al server per la prima volta. Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve utilizzare fino al completamento dell'accesso. È possibile utilizzare criteri di gruppo per definire queste impostazioni nei registri dei computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server. Nella tabella seguente sono elencate le impostazioni di criteri di gruppo disponibili per Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Impostazione dei criteri di gruppo per Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione dei criteri di gruppo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Specificare il server<br />
ConfigurationMode</p></td>
<td><p>Specifica il modo in cui Lync 2013 identifica il trasporto e il server da utilizzare durante l'accesso. All'interno di questa impostazione, è necessario specificare quanto segue:</p>
<ul>
<li><p>ServerAddressExternal: specifica il nome o l'indirizzo IP del server utilizzato dai client e dai contatti federati quando si effettua la connessione dall'esterno del firewall esterno.</p></li>
<li><p>ServerAddressInternal: specifica il nome o l'indirizzo IP del server utilizzato quando i client si connettono dall'interno del firewall dell'organizzazione.</p></li>
<li><p>Transport: specifica il protocollo TCP (Transmission Control Protocol) o TLS (Transport Layer Security).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versioni di server aggiuntive supportate<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Specifica un elenco di nomi di versioni server separati da punti e virgola a cui Lync Server 2013 accederà, oltre alle versioni server supportate per impostazione predefinita.</p></td>
</tr>
<tr class="odd">
<td><p>Disabilitare il caricamento automatico dei log degli errori di accesso (DisableAutomaticSendTracing)</p></td>
<td><p>Carica automaticamente i log degli errori di accesso a Lync Server per l'analisi. Se l'accesso ha esito positivo, non vengono caricati automaticamente i registri. Se questo criterio non è configurato, si verifica quanto segue:</p>
<dl>
<dt><span></span></dt>
<dd><p>Per gli utenti di Lync Online: i log di errore di accesso vengono caricati automaticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Per gli utenti locali di Lync: viene visualizzata una finestra di dialogo di conferma all'utente prima del caricamento.</p>
</dd>
</dl>
<p>Quando questa impostazione è disabilitata, i registri di accesso vengono caricati automaticamente nel server Lync per gli utenti di Lync locale e di Lync Online. Quando questa impostazione è abilitata, i registri di accesso non vengono mai caricati automaticamente.</p></td>
</tr>
<tr class="even">
<td><p>Disabilitare il fallback HTTP per la connessione SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impedisce a Lync Server di tentare la connessione al server tramite HTTP, se TLS o TCP non sono disponibili. Per impostazione predefinita, Lync tenta innanzitutto di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto ha esito positivo, Lync tenta di connettersi tramite HTTP. Utilizzare questi criteri per disabilitare il tentativo di connessione HTTP di fallback.</p></td>
</tr>
<tr class="odd">
<td><p>Richiedi credenziali di accesso<br />
DisableNTCredentials</p></td>
<td><p>Richiede all'utente di fornire le credenziali di accesso per Lync anziché utilizzare automaticamente le credenziali di Windows durante l'accesso a un server SIP.</p></td>
</tr>
<tr class="even">
<td><p>Disabilitare il controllo della versione del server<br />
(DisableServerCheck)</p></td>
<td><p>Se si imposta questo criterio su 1, impedire a Lync di controllare il nome e la versione del server prima di eseguire l'accesso. Per impostazione predefinita, Lync effettua questi controlli prima di accedere.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'utilizzo di bit per scaricare i file del servizio Rubrica<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Consente a Lync di utilizzare BITS (Background Intelligent Transfer Service) per scaricare i file dei servizi della Rubrica.</p></td>
</tr>
<tr class="even">
<td><p>Configurare la modalità di sicurezza SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Consente a Lync di inviare e ricevere messaggi istantanei in modo più sicuro. Tale criterio non produce alcun effetto sui servizi di Windows .NET o Microsoft Exchange Server.</p>
<p>Se non si configura questa impostazione di criterio, Lync può utilizzare qualsiasi trasporto. Tuttavia, se non utilizza TLS e se il server esegue l'autenticazione degli utenti, Lync deve utilizzare l'autenticazione NTLM o Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Global Address Book scaricare il ritardo iniziale<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Specifica il periodo di tempo che deve trascorrere prima che si verifichi un download dell'elenco indirizzi globale. Il valore predefinito è 60 minuti, il che significa che il server ritarderà il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.</p></td>
</tr>
<tr class="even">
<td><p>Impedire agli utenti di eseguire Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impedisce l'esecuzione di Lync da parte degli utenti. È possibile configurare questa impostazione di criterio sia in Configurazione computer che in Configurazione utente, ma l'impostazione in Configurazione computer ha la precedenza.</p></td>
</tr>
<tr class="odd">
<td><p>Consenti archiviazione delle password degli utenti<br />
(SavePassword)</p></td>
<td><p>Consente a Lync di archiviare le password.</p></td>
</tr>
<tr class="even">
<td><p>Configurare la modalità di compressione SIP<br />
SipCompression</p></td>
<td><p>Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tenere presente che l'impostazione di questo criterio potrebbe comportare un aumento del tempo di accesso.</p></td>
</tr>
<tr class="odd">
<td><p>Elenco di domini attendibili<br />
(TrustModelData)</p></td>
<td><p>Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.</p></td>
</tr>
</tbody>
</table>


I criteri configurati nel server hanno la priorità sulle impostazioni di Criteri di gruppo e sulle opzioni client configurate dall'utente. Nella tabella riportata di seguito viene riepilogato l'ordine di priorità delle impostazioni in caso di conflitto.

### <a name="group-policy-precedence"></a>Priorità di Criteri di gruppo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedenza</th>
<th>Percorso o metodo di impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>Lync Server 2013 provisioning in-band</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>La finestra di dialogo Lync-Opzioni in Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Per definire le impostazioni di criteri di gruppo mediante i file del modello amministrativo di Lync 2013

1.  Creare una cartella di livello radice che contenga tutti i file ADMX indipendenti dalla lingua. Ad esempio, creare la cartella radice per l'archivio centrale nel controller di dominio in questo percorso:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > In questa procedura si presuppone che si desideri gestire più computer nel dominio. In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario. In questo modo viene fornito un percorso di archiviazione centrale replicato per i modelli amministrativi di dominio.

    
    </div>

2.  Creare una sottocartella per ogni lingua che verrà utilizzata. Tali sottocartelle conterranno i file di risorse ADML specifici per la lingua. Ad esempio, creare una sottocartella per gli Stati Uniti (EN-US) in questa posizione:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

