---
title: "Lync Server 2013: pianificazione dell'autenticazione a due fattori"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973a1eeb704788eb07e02afc502ac4bbe41544c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Pianificazione dell'autenticazione a due fattori in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-04-06_

Di seguito è riportato un elenco di considerazioni sulla distribuzione durante la configurazione di un ambiente Microsoft Lync Server 2013 per il supporto dell'autenticazione a due fattori.

<div>

## <a name="client-support"></a>Supporto client

Gli aggiornamenti cumulativi di Lync 2013 per Lync Server 2013: luglio 2013 client desktop e tutti i client mobili attualmente supportano l'autenticazione a due fattori.

</div>

<div>

## <a name="topology-requirements"></a>Requisiti della topologia

I clienti sono fortemente incoraggiati a distribuire l'autenticazione a due fattori utilizzando Lync Server 2013 dedicato con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Edge, Director e pool di utenti. Per abilitare l'autenticazione passiva per gli utenti di Lync, è necessario che altri metodi di autenticazione siano disabilitati per altri ruoli e servizi, tra cui i seguenti:


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
<th>Server Role</th>
<th>Tipo di autenticazione da disabilitare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web Service</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos, NTLM e certificato</p></td>
</tr>
<tr class="even">
<td><p>Web Service</p></td>
<td><p>WebServer</p></td>
<td><p>Front End</p></td>
<td><p>Kerberos, NTLM e certificato</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrar</p></td>
<td><p>Front End</p></td>
<td><p>Kerberos e NTLM</p></td>
</tr>
</tbody>
</table>


A meno che questi tipi di autenticazione non siano disabilitati a livello di servizio, tutte le altre versioni del client Lync non saranno in grado di accedere correttamente dopo che è stata abilitata l'autenticazione a due fattori all'interno della distribuzione.

</div>

<div>

## <a name="lync-service-discovery"></a>Individuazione del servizio Lync

I record DNS utilizzati dai client interni e/o esterni per individuare i servizi Lync devono essere configurati in modo da essere risolti in un server Lync che non è abilitato per l'autenticazione a due fattori. Con questa configurazione, non è necessario che gli utenti provenienti da pool Lync che non sono abilitati per l'autenticazione a due fattori immettano un PIN per l'autenticazione, mentre gli utenti provenienti da pool Lync abilitati per l'accesso a due fattori dovranno immettere il proprio PIN per autenticare.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticazione di Exchange

I clienti che hanno distribuito l'autenticazione a due fattori per Microsoft Exchange possono rilevare che alcune caratteristiche nel client Lync non sono disponibili. Questo è attualmente in fase di progettazione, in quanto il client Lync non supporta l'autenticazione a due fattori per le caratteristiche che dipendono dall'integrazione di Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contatti di Lync

Gli utenti di Lync configurati per sfruttare la caratteristica archivio contatti unificato troveranno che i loro contatti non sono più disponibili dopo aver eseguito l'accesso con l'autenticazione a due fattori.

È consigliabile utilizzare il cmdlet **Invoke-CsUcsRollback** per rimuovere i contatti utente esistenti dall'archivio contatti unificato e archiviarli in Lync Server 2013 prima di abilitare l'autenticazione a due fattori.

</div>

<div>

## <a name="skill-search"></a>Ricerca skill

I clienti che hanno configurato la funzionalità di ricerca Skill nell'ambiente Lync troveranno che questa funzionalità non funziona quando Lync è abilitato per l'autenticazione a due fattori. Questo è in base alla progettazione, in quanto Microsoft SharePoint attualmente non supporta l'autenticazione a due fattori.

</div>

<div>

## <a name="lync-credentials"></a>Credenziali di Lync

Sono presenti diverse considerazioni sulla distribuzione che coinvolgono credenziali di Lync salvate che possono influire sugli utenti configurati per l'utilizzo dell'autenticazione a due fattori.

<div>

## <a name="deleting-saved-credentials"></a>Eliminazione delle credenziali salvate

Gli utenti del client desktop devono utilizzare l'opzione **delete my Sign-in info** nel client Lync ed eliminare la cartella del profilo SIP da%\\localappdata\\%\\Microsoft\\Office 15,0 Lync prima di tentare di firmare per la prima volta utilizzando l'autenticazione a due fattori.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Con il metodo di autenticazione Kerberos o NTLM, le credenziali di Windows dell'utente vengono utilizzate automaticamente per l'autenticazione. In una distribuzione tipica di Lync Server 2013 in cui Kerberos e/o NTLM è abilitato per l'autenticazione, gli utenti non devono immettere le proprie credenziali ogni volta che accedono.

Se agli utenti vengono richieste involontariamente le credenziali prima che venga richiesto di immettere il proprio PIN, la chiave del registro di sistema **DisableNTCredentials** potrebbe essere involontariamente configurata nei computer client, possibilmente tramite criteri di gruppo.

Per impedire la richiesta aggiuntiva di credenziali, creare la seguente voce del registro di sistema nella workstation locale o utilizzare il modello di amministrazione di Lync da applicare a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:

Criteri\_\\software\_\\del\\computer locale di\\HKEY\\Microsoft\\Office 15,0 Lync

DWORD\_reg: DisableNTCredentials

Valore: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Quando un utente accede a Lync per la prima volta, all'utente viene richiesto di salvare la propria password. Se selezionata, questa opzione consente di archiviare il certificato client dell'utente nell'archivio certificati personale e le credenziali di Windows dell'utente da archiviare in Gestione credenziali del computer locale.

L'impostazione del registro di sistema **SavePassword** deve essere disattivata quando Lync è configurato per supportare l'autenticazione a due fattori. Per impedire agli utenti di salvare le password, modificare la voce del registro di sistema seguente nella workstation locale o utilizzare il modello di amministrazione di Lync per applicarlo a tutti gli utenti di un determinato pool utilizzando criteri di gruppo:

Software\_\\utente\_\\corrente di HKEY\\Microsoft\\Office\\15,0 Lync

DWORD\_reg: SavePassword

Valore: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Riproduzione di token AD FS 2,0

AD FS 2,0 fornisce una funzionalità denominata rilevamento della riproduzione di token, in base al quale è possibile rilevare più richieste di token utilizzando lo stesso token e quindi eliminarle. Quando questa funzionalità è abilitata, il rilevamento della riproduzione di token protegge l'integrità delle richieste di autenticazione sia nel profilo passivo WS-Federation che nel profilo WebSSO SAML assicurandosi che lo stesso token non venga mai utilizzato più di una volta.

Questa funzionalità deve essere abilitata in situazioni in cui la sicurezza è un problema molto elevato, ad esempio quando si utilizzano i chioschi. Per ulteriori informazioni sul rilevamento della riproduzione di token, vedere procedure consigliate per la pianificazione e la distribuzione sicure [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215)di ad FS 2,0 all'indirizzo.

</div>

<div>

## <a name="external-user-access"></a>Accesso utente esterno

La configurazione di un proxy AD FS o di un proxy inverso per il supporto dell'autenticazione a due fattori di Lync dalle reti esterne non è illustrata in questi argomenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

