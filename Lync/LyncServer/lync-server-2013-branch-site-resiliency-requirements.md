---
title: 'Lync Server 2013: Requisiti di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisiti di resilienza dei siti di succursale per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-25_

Questo argomento consente di preparare gli utenti per la sopravvivenza della filiale e della segreteria telefonica e specifica anche i requisiti hardware e software pertinenti.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparazione degli utenti della filiale per la resilienza del sito filiale

Preparare gli utenti per la resilienza del sito di succursale impostando il pool di registrar come Survivable Branch Appliance (SBA) o Survivable Branch Server.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Assegnazioni del registrar per gli utenti della filiale

Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, è necessario assegnare un registrar principale a ogni utente. Gli utenti del sito succursale devono sempre registrarsi con il Registrar presso il sito della filiale, indipendentemente dal fatto che il registrar si trovi nella Survivable Branch Appliance, Survivable Branch Server o nel server autonomo Lync Server 2013 standard o Enterprise Edition. È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il pool di registrar. Se il Survivable Branch Appliance diventa non disponibile, questo è il modo in cui i client del sito Branch verranno automaticamente individuati nel registrar.

Se un sito di succursale non ha un server DNS, esistono due modi alternativi per configurare l'individuazione di Survivable Branch Appliance o Survivable Branch Server:

  - Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito della filiale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server.

  - Configurare Survivable Branch Appliance o Survivable Branch Server per rispondere alle query di 120 DHCP.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Routing vocale per gli utenti di Branch

È consigliabile creare un criterio VoIP (Voice over Internet Protocol) separato per gli utenti in un sito di succursale. Questo criterio deve includere una route primaria che usa il gateway Survivable Branch Appliance o Branch Server e una o più route di backup che usano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale. Se la route principale non è disponibile, viene usata invece la route di backup che usa uno o più gateway di sito centrale. In questo modo, indipendentemente dalla posizione in cui un utente è registrato, nel registrar del sito succursale o nel pool di registrazione del backup presso il sito centrale, il criterio VoIP dell'utente è sempre attivo. Si tratta di una considerazione importante per gli scenari di failover. Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare Survivable Branch Appliance per connettersi a un pool di registrar di backup presso il sito centrale, è necessario trasferire gli utenti del sito della filiale nel sito centrale per la durata. Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere l' [Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) nella documentazione relativa alla distribuzione. Se gli utenti non hanno criteri VoIP a livello di utente o piani di chiamata a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i piani di chiamata a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché i criteri VoIP a livello di sito del sito di succursale e i dial plan. In questo scenario, a meno che i criteri VoIP a livello di sito e i piani di chiamata a livello di sito usati dal pool di registrazione di backup possano essere applicati anche agli utenti del sito succursale, le chiamate non riusciranno. Ad esempio, se gli utenti di un sito di filiale che si trovano in Giappone vengono spostati in un sito centrale di Redmond, un dial plan con regole di normalizzazione che prevedono + 1425 a tutte le chiamate a 7 cifre è improbabile che si traducano in modo appropriato le chiamate per tali utenti.

<div>


> [!IMPORTANT]  
> Quando si crea una route di backup di una filiale, è consigliabile aggiungere due record di utilizzo PSTN al criterio utente della filiale e assegnare le route separate a ognuna di esse. La route First o Primary indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o Branch Server; la route secondo o backup consentirebbe di indirizzare le chiamate al gateway nel sito centrale. In indirizzamento delle chiamate, l'SBA o il server di succursale tenterà tutte le route assegnate al primo record di utilizzo PSTN prima di tentare il secondo record di utilizzo.



</div>

Per assicurarti che le chiamate in ingresso agli utenti del sito succursale raggiungano questi utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (il che accadrebbe, ad esempio, se il Survivable Branch Appliance o Branch il gateway non è più disponibile per la manutenzione), crea una route di failover nel gateway (o usa il provider di chiamate dirette in diretta) per reindirizzare le chiamate in arrivo al pool di registrazione del backup presso il sito centrale. Da lì le chiamate verranno instradate sul collegamento WAN agli utenti di Branch. Assicurarsi che la route traguardi i numeri in modo che siano conformi al gateway PSTN o ad altri formati di numeri di telefono accettati del peer trunk. Per informazioni dettagliate sulla creazione di una route di failover, vedere [configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Creare anche piani di chiamata a livello di servizio per il trunk associato al gateway nel sito della filiale per normalizzare le chiamate in arrivo. Se si dispone di due appliance Survivable Branch in un sito di succursale, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano separato a livello di servizio.

<div>


> [!NOTE]  
> Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito di succursale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse registrato presso il sito centrale. Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.



</div>

Ti consigliamo anche di creare un dial plan a livello di utente e un criterio vocale e quindi assegnarlo agli utenti del sito succursale. Per informazioni dettagliate, vedere [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="routing-extension-numbers"></a>Numeri di interno di routing

Quando si preparano i dial plan e i criteri vocali per gli utenti del sito succursale, assicurarsi di includere regole di normalizzazione e regole di traduzione corrispondenti alle stringhe e al formato numerico usati nell'attributo msRTCSIP-line (o URI di linea), in modo che le chiamate di Lync 2013 siano abilitate tra Branch Gli utenti del sito e gli utenti del sito centrale verranno instradati correttamente, in particolare quando le chiamate devono essere reinstradate tramite la rete PSTN perché il collegamento WAN non è disponibile. Ci sono inoltre considerazioni speciali per i numeri composti che includono numeri di interno, ma solo numeri di telefono.

Regole di normalizzazione e traduzioni che corrispondono a URI di linea che contengono un numero di interno, sia in esclusiva che in aggiunta a un numero di telefono E. 164 completo, hanno requisiti aggiuntivi. Questa sezione descrive diversi scenari di esempio per instradare le chiamate per gli URI di linea con un numero di interno.

Se l'organizzazione non ha numeri di telefono diretti per singoli utenti e l'URI di linea di ogni utente è configurato con *solo* un numero di interno, gli utenti interni possono chiamarsi a vicenda componendo solo un numero di interno. Tuttavia, è necessario configurare le regole di normalizzazione che possono essere applicate alle chiamate da un utente di un sito di succursale a un utente del sito centrale, che corrispondono ai numeri di interno.

In uno scenario in cui il collegamento WAN tra un sito di succursale e un sito centrale è disponibile, le chiamate dagli utenti del sito della filiale agli utenti del sito centrale non richiedono la regola di normalizzazione corrispondente per tradurre il numero perché la chiamata non viene instradata tramite la rete PSTN. Ad esempio:


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome regola</th>
<th>Descrizione</th>
<th>Schema numerico</th>
<th>Conversione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Non traduce i numeri a 5 cifre</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 non viene tradotto</p></td>
</tr>
</tbody>
</table>


È inoltre necessario includere i numeri di interno per scenari specifici, ad esempio quando il collegamento WAN tra un sito di succursale e un sito centrale non è disponibile e una chiamata da un sito di succursale deve essere instradata tramite la rete PSTN. Durante un'interruzione WAN, se un utente del sito filiale chiama un utente del sito centrale solo tramite la chiamata dell'estensione dell'utente del sito centrale, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'utente del sito centrale. Se l'URI di linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente invece di un numero di telefono completo univoco per l'utente, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'organizzazione. . Ad esempio:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Modello di corrispondenza</th>
<th>Conversione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Converte i numeri a 5 cifre in un numero di telefono e un'estensione di un utente</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; ext = $1</p></td>
<td><p>10001 viene convertito in + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>Converte i numeri a 5 cifre nel numero di telefono dell'organizzazione e nell'estensione di un utente</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100; ext = $1</p></td>
<td><p>10001 viene convertito in + 14255550100; ext = 10001</p></td>
</tr>
</tbody>
</table>


In questo scenario, se il peer trunk che gestisce il reinstradamento alla rete PSTN non supporta i numeri di interno, la regola di traduzione in uscita deve anche rimuovere il numero di interno. Ad esempio:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrizione</th>
<th>Modello di corrispondenza</th>
<th>Conversione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rimuove l'estensione dai numeri di telefono con le estensioni</p></td>
<td><p>^\+(\d *); EXT = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+ 14255550123; ext = 10001 viene tradotto in + 14255550123</p></td>
</tr>
</tbody>
</table>


Indipendentemente dal fatto che sia disponibile un collegamento WAN, se l'organizzazione non ha numeri DID configurati per singoli utenti e l'URI di linea per un utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare il URI della linea numero di telefono dell'organizzazione con un numero raggiungibile dal peer trunk o dal gateway PSTN del sito della filiale. Devi anche configurare l'URI della linea di numeri di telefono dell'organizzazione per includere la relativa estensione univoca per le chiamate da instradare al numero.

Per informazioni dettagliate sulle chiamate da un utente del sito centrale a un utente di un sito di succursale quando il collegamento WAN tra i siti non è disponibile, vedere "preparazione per la sopravvivenza della segreteria telefonica" più avanti in questo argomento. Per informazioni dettagliate sui dial plan e sulle regole di normalizzazione, incluse altre regole di esempio, vedere [dial plan e regole di normalizzazione in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione di pianificazione e [configurazione di dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulle regole di traduzione in uscita, vedere [regole di traduzione in Lync server 2013](lync-server-2013-translation-rules.md) nella documentazione relativa alla pianificazione e [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Preparazione per la sopravvivenza della segreteria telefonica

La messaggistica unificata di Exchange viene in genere installata solo in un sito centrale e non nei siti di succursale. Un chiamante dovrebbe essere in grado di uscire da un messaggio di segreteria telefonica, anche se il collegamento WAN tra sito di succursale e sito centrale non è disponibile. Di conseguenza, la configurazione dell'URI di linea per il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti del sito filiale richiede considerazioni particolari, oltre al criterio vocale, al dial plan e alle regole di normalizzazione applicabili alla segreteria telefonica. numero.

Survivable Branch Appliances (SBAs) e Survivable Branch Servers garantiscono la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN. In particolare, se si usa un Survivable Branch Appliance o Survivable Branch Server e la WAN non è disponibile, l'SBA o Survivable Branch Server reindirizza le chiamate senza risposta tramite la rete PSTN alla messaggistica unificata di Exchange nel sito centrale. Con un SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi della segreteria telefonica tramite la rete PSTN durante un'interruzione WAN. Infine, durante un'interruzione WAN il Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di mancata chiamata e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinata la rete WAN. Per assicurarti che il reindirizzamento della segreteria telefonica sia resiliente, assicurati di aggiungere una voce per il nome di dominio completo del pool di siti centrali e una voce per il nome di dominio completo del server perimetrale nel file hosts nel Survivable Branch Server. In caso contrario, la risoluzione DNS può uscire se non si dispone di un server DNS presso il sito della filiale.

Per gli utenti del sito succursale è consigliabile disporre delle configurazioni seguenti per la sopravvivenza della segreteria telefonica:

  - Un amministratore di Microsoft Exchange deve configurare l'operatore automatico di messaggistica unificata di Exchange (AA) per accettare solo i messaggi. Questa configurazione Disabilita tutte le altre funzionalità generiche, ad esempio il trasferimento a un utente o il trasferimento a un operatore, e limita l'AA ad accettare solo i messaggi. In alternativa, l'amministratore di Exchange può usare un generico AA o un AA personalizzato per instradare la chiamata a un operatore.

  - L'amministratore di Lync Server deve assumere il numero di telefono AA e utilizzare tale numero come numero di **operatore automatico di messaggistica unificata di Exchange** nelle impostazioni di reinstradazione della segreteria telefonica per Survivable Branch Appliance o Branch Server.

  - L'amministratore di Lync Server dovrebbe ottenere il numero di telefono per l'accesso abbonato alla messaggistica unificata di Exchange e usare tale numero come numero di **accesso del Sottoscrittore** nelle impostazioni di reindirizzamento della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server.

  - L'amministratore di Lync Server deve configurare la messaggistica unificata di Exchange in modo che solo un dial plan sia associato a tutti gli utenti della filiale che hanno bisogno di accedere alla segreteria telefonica durante un'interruzione WAN.

  - Quando il collegamento WAN non è disponibile, le chiamate agli utenti del sito succursale possono essere indirizzate alla segreteria telefonica di Exchange Unified Messaging (UM) dell'utente, ma solo se il criterio vocale applicato alla chiamata specifica un numero di telefono della segreteria telefonica univoco e non include un'estensione numero.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisiti hardware e software per la resilienza del sito filiale

I requisiti hardware e software variano a seconda della soluzione di resilienza.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisiti per gli elettrodomestici Survivable Branch

Hardware e software obbligatori sono integrati nell'appliance Survivable Branch. Tuttavia, è consigliabile anche che ogni sito della filiale distribuisca un server DHCP per ottenere gli indirizzi IP del client. in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.

Se i server DNS aziendali si trovano solo nei siti centrali, gli utenti del sito della succursale non potranno connettersi a questi ultimi durante un'interruzione WAN e quindi l'individuazione di Lync Server che usa il record DNS SRV (SRV) non riuscirà. Per assicurare il reinstradamento rapido durante un'interruzione WAN, i record DNS devono essere memorizzati nella cache del sito della filiale. Se il router della filiale lo supporta, attivare la memorizzazione nella cache DNS. In alternativa, è possibile distribuire un server DNS presso la filiale. Può trattarsi di un server autonomo o di una versione dell'appliance Survivable Branch che supporta le funzionalità DNS. Per informazioni dettagliate, contattare il provider Survivable Branch Appliance.

<div>


> [!NOTE]  
> Non è necessario disporre di un controller di dominio in un sito di succursale. Il Survivable Branch Appliance autentica i client usando un certificato speciale che invia il client in risposta alla richiesta di certificato del client quando viene eseguita la firma.



</div>

I client Lync possono individuare il server Lync usando l'opzione DHCP 120 (opzione registrar SIP). Questa operazione può essere configurata in uno dei due modi seguenti:

  - Configurare il server DHCP presso il sito della filiale per rispondere alle query di 120 DHCP, che restituiscono il nome di dominio completo del registrar nel Survivable Branch Appliance o Survivable Branch Server.

  - Attivare il protocollo DHCP di Lync Server. Quando questo è attivato, il registrar di Lync Server risponde alle query di opzione 120 per DHCP. Tieni presente che il registrar non risponde a nessuna query DHCP diversa dalle opzioni DHCP 120.

Inoltre, per i siti di succursale più grandi con più subnet, gli agenti di inoltro DHCP devono essere abilitati per inoltrare query DHCP Option 120 al server DHCP (configurazione 1) o al registrar (configurazione 2).

Infine, gli utenti del sito succursale devono essere configurati per VoIP aziendale e provisioning con un endpoint di comunicazioni unificato appropriato.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisiti per Survivable Branch Servers

I requisiti per i Survivable Branch Server corrispondono ai requisiti per un server front-end. Per informazioni dettagliate, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisiti per distribuzioni a livello di sito di Lync Server su vasta scala

Per informazioni dettagliate, vedere [determinazione dei requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

