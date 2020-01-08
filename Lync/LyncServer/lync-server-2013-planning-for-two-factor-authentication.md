---
title: "Lync Server 2013: pianificazione per l'autenticazione a due fattori"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d2328ee11ffb893974e48b86922123145ed72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Pianificazione dell'autenticazione a due fattori in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-04-06_

Di seguito è riportato un elenco di considerazioni sulla distribuzione quando si configura un ambiente di Microsoft Lync Server 2013 per supportare l'autenticazione a due fattori.

<div>

## <a name="client-support"></a>Supporto client

Gli aggiornamenti cumulativi di Lync 2013 per Lync Server 2013: client desktop di luglio 2013 e tutti i client mobili supportano attualmente l'autenticazione a due fattori.

</div>

<div>

## <a name="topology-requirements"></a>Requisiti di topologia

I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori con Lync Server dedicato 2013 con gli aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Edge, Director e pool di utenti. Per abilitare l'autenticazione passiva per gli utenti di Lync, è necessario disabilitare altri metodi di autenticazione per altri ruoli e servizi, inclusi i seguenti:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di configurazione</th>
<th>Tipo di servizio</th>
<th>Ruolo del server</th>
<th>Tipo di autenticazione da disabilitare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servizio Web</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos, NTLM e certificato</p></td>
</tr>
<tr class="even">
<td><p>Servizio Web</p></td>
<td><p>WebServer</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos, NTLM e certificato</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Bordo</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrar</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
</tbody>
</table>


A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client Lync non saranno in grado di accedere correttamente quando l'autenticazione a due fattori è abilitata all'interno della distribuzione.

</div>

<div>

## <a name="lync-service-discovery"></a>Individuazione di servizi Lync

I record DNS usati dai client interni e/o esterni per individuare i servizi Lync devono essere configurati per la risoluzione in un server Lync non abilitato per l'autenticazione a due fattori. Con questa configurazione, gli utenti provenienti da pool Lync non abilitati per l'autenticazione a due fattori non saranno necessari per immettere un PIN da autenticare, mentre agli utenti provenienti da pool Lync abilitati per l'autenticazione a due fattori verrà richiesto di immettere il proprio PIN per autenticare.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticazione di Exchange

I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange potrebbero non essere disponibili per alcune funzionalità del client Lync. Questa funzionalità è attualmente in fase di progettazione, poiché il client Lync non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contatti di Lync

Gli utenti di Lync configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo l'accesso con l'autenticazione a due fattori.

È consigliabile usare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Lync Server 2013 prima di abilitare l'autenticazione a due fattori.

</div>

<div>

## <a name="skill-search"></a>Ricerca di abilità

I clienti che hanno configurato la funzionalità Ricerca competenze nell'ambiente Lync troveranno che questa caratteristica non funziona quando Lync è abilitato per l'autenticazione a due fattori. In base alla progettazione, poiché in Microsoft SharePoint non è attualmente supportata l'autenticazione a due fattori.

</div>

<div>

## <a name="lync-credentials"></a>Credenziali di Lync

Sono disponibili diverse considerazioni sulla distribuzione che includono credenziali di Lync salvate che possono influire sugli utenti configurati per l'uso dell'autenticazione a due fattori.

<div>

## <a name="deleting-saved-credentials"></a>Eliminazione delle credenziali salvate

Gli utenti del client desktop devono usare l'opzione **Elimina le informazioni di accesso** nel client Lync ed eliminare la cartella del profilo SIP da% LocalAppData\\%\\Microsoft\\Office\\15,0 Lync prima di provare a firmare per la prima volta con l'autenticazione a due fattori.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono usate automaticamente per l'autenticazione. In una distribuzione tipica di Lync Server 2013 in cui è abilitato Kerberos e/o NTLM per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che eseguono l'accesso.

Se agli utenti vengono richieste involontariamente le credenziali prima che venga chiesto di immettere il PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere configurata involontariamente nei computer client, possibilmente tramite criteri di gruppo.

Per evitare la richiesta aggiuntiva per le credenziali, creare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo di Lync per applicare tutti gli utenti per un pool specifico tramite criteri di gruppo:

Criteri\_\\di\_HKEY\\del\\software locale\\di\\Microsoft\\Office 15,0 Lync

DWORD\_reg: DisableNTCredentials

Valore: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Quando un utente accede a Lync per la prima volta, all'utente viene chiesto di salvare la propria password. Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio dei certificati personali e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.

L'impostazione del registro di sistema **SavePassword** deve essere disabilitata quando Lync è configurato per supportare l'autenticazione a due fattori. Per impedire agli utenti di salvare le password, modificare la voce del registro di sistema seguente nella workstation locale o usare il modello amministrativo di Lync per applicare tutti gli utenti per un pool specifico tramite criteri di gruppo:

HKEY\_software\_\\utente\\corrente Microsoft\\Office\\15,0\\Lync

DWORD\_reg: SavePassword

Valore: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Riproduzione di token AD FS 2,0

ADFS 2,0 offre una caratteristica denominata rilevamento riproduzione token, in base alla quale più richieste di token che usano lo stesso token possono essere rilevate e quindi scartate. Quando questa funzionalità è abilitata, il rilevamento della riproduzione del token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo WS-Federation che nel profilo WebSSO SAML assicurando che lo stesso token non venga mai usato più di una volta.

Questa caratteristica deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si usano i chioschi. Per altre informazioni sul rilevamento della riproduzione di token, vedere procedure consigliate per la pianificazione e la distribuzione sicure [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)di ADFS 2,0 at.

</div>

<div>

## <a name="external-user-access"></a>Accesso utenti esterni

La configurazione di un proxy ADFS o di un proxy inverso per supportare l'autenticazione a due fattori di Lync da reti esterne non è contemplata in questi argomenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

