---
title: 'Lync Server 2013: requisiti di resilienza dei siti di succursale'
description: 'Lync Server 2013: requisiti di resilienza dei siti di succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef05917fb53d1333895236e849cb54596cc41947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555082"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisiti di resilienza dei siti di succursale per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-25_

In questo argomento vengono fornite informazioni utili per preparare gli utenti per la resilienza dei siti di succursale e per il funzionamento continuato (survivability) della segreteria telefonica e vengono specificati i requisiti hardware e software pertinenti.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparazione degli utenti di succursale per la resilienza del sito di succursale

Preparare gli utenti per la resilienza dei siti di succursale impostando il pool di registrazione come Survivable Branch Appliance (SBA) o Survivable Branch Server.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Assegnazioni di registrazione per utenti di succursale

Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, è necessario assegnare un Registrar primario a ciascun utente. Gli utenti del sito di succursale devono sempre registrarsi con il registrar nel sito di succursale, indipendentemente dal fatto che il registrar risieda nel Survivable Branch Appliance, nel Survivable Branch Server o nel server autonomo Lync Server 2013 standard o Enterprise Edition. È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il pool di registrazione. Se il Survivable Branch Appliance non è disponibile, questo è il modo in cui i client dei siti di succursale scopriranno automaticamente la registrazione di backup.

Se un sito di succursale non dispone di un server DNS, esistono due modi alternativi per configurare l'individuazione del Survivable Branch Appliance o Survivable Branch Server:

  - Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito di succursale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server.

  - Configurare il Survivable Branch Appliance o il Survivable Branch Server per rispondere alle query DHCP 120.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Routing vocale per gli utenti di succursale

Per gli utenti di un sito di succursale è consigliabile creare criteri VoIP (Voice over Internet Protocol) a livello di utente separati. Questo criterio deve includere una route principale che utilizza il Survivable Branch Appliance o il gateway del server di succursale e una o più route di backup che utilizzano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale. Se la route principale non è disponibile, viene sostituita dalla route di backup, che può utilizzare uno o più gateway del sito centrale. In questo modo, non è rilevante se l'utente è registrato presso la funzione di registrazione del sito di succursale o presso il pool di registrazione di backup nel sito centrale: i criteri VoIP dell'utente saranno sempre attivi. Questa considerazione è particolarmente importante per gli scenari di failover. Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare il Survivable Branch Appliance per connettersi a un pool di registrazione di backup nel sito centrale, è necessario spostare gli utenti dei siti di succursale nel sito centrale per tutta la durata. Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere l' [Appendice B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) nella documentazione relativa alla distribuzione. Se gli utenti non dispongono di criteri VoIP a livello di utente o di dial plan a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i dial plan a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché i criteri VoIP a livello di sito di succursale e i dial plan. In questo scenario le chiamate degli utenti del sito di succursale avranno esito positivo se a tali utenti non è possibile applicare i criteri VoIP e i dial plan a livello di sito utilizzati dal pool di registrazione di backup. Se ad esempio gli utenti di un sito di succursale situato in Giappone vengono spostati in un sito centrale situato a Redmond, è improbabile che un dial plan con regole di normalizzazione che antepongono il prefisso +1425 a tutte le chiamate a numeri di sette cifre sia in grado di convertire correttamente le chiamate di tali utenti.

<div>


> [!IMPORTANT]  
> Quando si crea una route di backup per una succursale, è consigliabile aggiungere ai criteri utente della succursale due record di utilizzo telefono PSTN e assegnare route distinte a ognuno. La prima route o Primary indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o a Branch Server; la seconda route o backup consentirebbe di indirizzare le chiamate al gateway nel sito centrale. Per l'indirizzamento delle chiamate, l'SBA o il server di succursale dovrà tentare tutte le route assegnate al primo record di utilizzo PSTN prima di tentare quelle del secondo record di utilizzo.



</div>

Per garantire che le chiamate in ingresso agli utenti dei siti di succursale raggiungano tali utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (cosa che accadrebbe, ad esempio, se il Survivable Branch Appliance o il gateway di succursale è stato premuto per la manutenzione), creare una route di failover sul gateway (o collaborare con il provider di composizione Direct inverso) per reindirizzare le chiamate in arrivo al pool di registrazione di backup nel sito centrale. Dal pool di registrazione di backup del sito centrale le chiamate verranno instradate agli utenti di succursale attraverso il collegamento WAN. Verificare che la route sia in grado di convertire i numeri nei formati di numero di telefono consentiti per il gateway PSTN o un altro trunk peer. Per informazioni dettagliate sulla creazione di una route di failover, vedere [configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Per consentire la normalizzazione delle chiamate in arrivo da parte del trunk associato al gateway del sito di succursale, è inoltre necessario creare dial plan a livello di servizio. Se in un sito di succursale sono disponibili due Survivable Branch Appliance, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano di servizio separato per ognuno di essi.

<div>


> [!NOTE]  
> Per tenere conto del consumo delle risorse del sito centrale da parte degli utenti dei siti di succursale che si appoggiano al sito centrale per le funzionalità di presenza, conferenza o failover, è consigliabile considerare ogni utente del sito di succursale come se fosse registrato presso il sito centrale. Al momento non sono presenti limiti al numero di utenti di siti di succursale, compresi gli utenti registrati con un Survivable Branch Appliance.



</div>

È inoltre consigliabile creare criteri vocali e di dial plan a livello di utente e quindi assegnarli agli utenti del sito di succursale. Per ulteriori informazioni, vedere [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [creare i criteri di routing VoIP per gli utenti di succursale in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="routing-extension-numbers"></a>Routing di numeri di interno

Quando si preparano i dial plan e i criteri vocali per gli utenti dei siti di succursale assicurarsi di includere regole di normalizzazione e regole di conversione che corrispondono alle stringhe e al formato numerico utilizzati nell'attributo msRTCSIP-line (o URI di linea), in modo che le chiamate di Lync 2013 abilitate tra gli utenti dei siti di succursale e gli utenti del sito centrale vengano instradate correttamente, in particolare quando le chiamate devono essere reinstradate sulla rete PSTN perché il collegamento WAN non Per i numeri composti contenenti numeri di interno, sono inoltre necessarie considerazioni specifiche rispetto ai numeri di telefono semplici.

Per le regole di normalizzazione e le regole di conversione corrispondenti a URI di linea contenenti un numero di interno, da solo o insieme a un numero di telefono E. 164 completo, esistono requisiti aggiuntivi. In questa sezione sono descritti alcuni scenari di esempio con l'indirizzamento di chiamate per URI di linea contenenti un numero di interno.

Se nell'organizzazione non sono configurati numeri di telefono DID (Direct Inward Dial) per utenti singoli e l'URI di linea di ogni utente è configurato con un *solo* numero di interno, gli utenti interni possono chiamarsi componendo solo il numero di interno desiderato. È tuttavia necessario configurare regole di normalizzazione applicabili alle chiamate da un utente di un sito di succursale a un utente del sito centrale corrispondenti ai numeri di interno.

In uno scenario in cui sia disponibile un collegamento WAN tra il sito di succursale e il sito centrale, per le chiamate tra utenti del sito di succursale e utenti del sito centrale non è necessaria la regola di normalizzazione per la conversione del numero, poiché la chiamata non viene indirizzata attraverso PSTN. Ad esempio:


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
<th>Formato numero</th>
<th>Translation</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Non converte i numeri a cinque cifre</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>$1</p></td>
<td><p>10001 non viene convertito</p></td>
</tr>
</tbody>
</table>


È inoltre necessario prevedere numeri di interno per scenari specifici in cui, ad esempio, il collegamento WAN tra un sito di succursale e il sito centrale non sia disponibile e sia necessario instradare tramite PSTN le chiamate provenienti dal sito di succursale. Se durante un'interruzione del funzionamento del collegamento WAN un utente di un sito di succursale chiama un utente del sito centrale componendo solo l'interno di quest'ultimo, è necessaria una regola di conversione in uscita che aggiunga il numero di telefono completo dell'utente del sito centrale. Se l'URI di linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente anziché il numero di telefono completo univoco dell'utente, è necessaria un regola di conversione in uscita che aggiunga il numero di telefono completo dell'organizzazione. Ad esempio:


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
<th>Formato corrispondente</th>
<th>Translation</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Converte i numeri a cinque cifre in numero di telefono e interno dell'utente corrispondente</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>+ 14255550123; ext = $1</p></td>
<td><p>10001 viene convertito in +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Converte i numeri a cinque cifre in numero di telefono dell'organizzazione e interno dell'utente corrispondente</p></td>
<td><p>^ (\d {5} ) $</p></td>
<td><p>+ 14255550100; ext = $1</p></td>
<td><p>10001 viene convertito in +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


In questo scenario, se i numeri di interno non sono supportati dal trunk peer che gestisce il reindirizzamento a PSTN, la regola di conversione in uscita deve inoltre prevedere la rimozione del numero di interno. Ad esempio:


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
<th>Formato corrispondente</th>
<th>Translation</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rimuove l'interno dai numeri di telefono con interno</p></td>
<td><p>^\+(\d *); EXT = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+14255550123;ext=10001 viene convertito in +14255550123</p></td>
</tr>
</tbody>
</table>


Indipendentemente dalla disponibilità di un collegamento WAN, se per l'organizzazione non sono configurati numeri DID per i singoli utenti e l'URI di linea di ogni utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare l'URI di linea del numero di telefono dell'organizzazione con un numero raggiungibile da parte del trunk peer o del gateway PSTN presso il sito di succursale. È inoltre necessario configurare l'URI di linea del numero di telefono dell'organizzazione in modo che includa l'interno univoco per le chiamate da indirizzare a tale numero.

Per informazioni dettagliate sulle chiamate da un utente del sito centrale a un utente di un sito di succursale in caso di indisponibilità del collegamento WAN tra i siti, vedere "Preparazione per il funzionamento continuato (survivability) della segreteria telefonica" più avanti in questo argomento. Per informazioni dettagliate sui dial plan e le regole di normalizzazione, incluse le altre regole di esempio, vedere [dial plans and normalizzation Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) nella documentazione relativa alla pianificazione e [configurazione dei dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulle regole di conversione in uscita, vedere [Translation Rules in Lync server 2013](lync-server-2013-translation-rules.md) nella documentazione relativa alla pianificazione e [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Preparazione per il funzionamento continuato (survivability) della segreteria telefonica

La messaggistica unificata di Exchange è in genere installata solo in un sito centrale e non nei siti di succursale. Il chiamante deve poter lasciare un messaggio nella segreteria telefonica anche quando il collegamento WAN tra il sito di succursale e il sito centrale non è disponibile. Di conseguenza, la configurazione dell'URI di linea per il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti dei siti di succursale richiede considerazioni speciali, oltre al criterio vocale, al dial plan e alle regole di normalizzazione applicabili a quel numero di segreteria telefonica.

Survivable Branch Appliances (SBA) e Survivable Branch Server offrono la sopravvivenza dei messaggi vocali per gli utenti di succursali durante un'interruzione della rete WAN. In particolare, se si utilizza un Survivable Branch Appliance o Survivable Branch Server e la rete WAN non è disponibile, l'ASB o il Survivable Branch Server reindirizza le chiamate senza risposta sulla rete PSTN alla messaggistica unificata di Exchange nel sito centrale. Con una SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi vocali tramite la rete PSTN durante un'interruzione della rete WAN. Infine, durante un'interruzione della rete WAN, Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di chiamata senza risposta e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinata la rete WAN. Per garantire che il reindirizzamento della segreteria telefonica sia resiliente, è necessario aggiungere una voce per il nome di dominio completo del pool di siti centrali e una voce per il nome di dominio completo del server perimetrale nel file hosts nel Survivable Branch Server. In caso contrario, se il sito di succursale non dispone di un server DNS, può verificarsi il timeout della risoluzione DNS.

Per configurare il funzionamento continuato (survivability) della segreteria telefonica per gli utenti dei siti di succursale, sono consigliate le configurazioni seguenti:

  - Un amministratore di Microsoft Exchange deve configurare l'operatore automatico di messaggistica unificata di Exchange (AA) per accettare solo i messaggi. Con questa configurazione viene disabilitata ogni altra funzionalità generica, ad esempio il trasferimento a un utente o al centralino. In alternativa, l'amministratore di Exchange può indirizzare le chiamate al centralino utilizzando Operatore automatico, generico o personalizzato.

  - L'amministratore di Lync Server deve assumere il numero di telefono AA e utilizzarlo come numero dell' **operatore automatico di messaggistica unificata di Exchange** nelle impostazioni di reinstradamento della segreteria telefonica per il Survivable Branch Appliance o il Branch Server.

  - L'amministratore di Lync Server dovrebbe ottenere il numero di telefono di accesso sottoscrittore Messaggistica unificata di Exchange e utilizzare tale numero come numero di **accesso del Sottoscrittore** nelle impostazioni di reinstradamento della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server.

  - L'amministratore di Lync Server deve configurare la messaggistica unificata di Exchange in modo che un solo dial plan sia associato a tutti gli utenti di succursale che devono accedere alla segreteria telefonica durante un'interruzione della rete WAN.

  - In caso di indisponibilità del collegamento WAN, le chiamate agli utenti dei siti di succursale possono essere instradate alla casella vocale di messaggistica unificata di Exchange degli utenti, ma solo se i criteri vocali applicati alle chiamate specificano un numero di telefono della segreteria telefonica univoco e senza numero di interno.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisiti hardware e software per la resilienza dei siti di succursale

I requisiti hardware e software variano a seconda della soluzione di resilienza in uso.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisiti per Survivable Branch Appliance

L'hardware e il software necessari sono incorporati nel Survivable Branch Appliance. Tuttavia, è consigliabile anche che ogni sito di succursale distribuisca un server DHCP per ottenere gli indirizzi IP del client; in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.

Se i server DNS dell'organizzazione si trovano solo in siti centrali, gli utenti dei siti di succursale non saranno in grado di connettersi a essi durante un'interruzione della rete WAN e pertanto l'individuazione di Lync Server che utilizza il record di risorse DNS SRV (SRV) avrà esito negativo. Per garantire il reindirizzamento rapido durante un'interruzione della rete WAN, i record DNS devono essere memorizzati nella cache nel sito di succursale. Se il router di succursale lo supporta, abilitare la memorizzazione nella cache DNS. In alternativa, è possibile distribuire un server DNS nel branch. Può trattarsi di un server autonomo o di una versione del Survivable Branch Appliance che supporta le funzionalità DNS. Per informazioni dettagliate, contattare il proprio provider di Survivable Branch Appliance.

<div>


> [!NOTE]  
> Presso un sito di succursale non è necessario un controller di dominio. Survivable Branch Appliance consente di autenticare i client utilizzando un certificato speciale che invia il client in risposta alla richiesta di certificato del client quando viene eseguita la firma.



</div>

I client Lync possono individuare Lync Server tramite l'opzione DHCP 120 (opzione di registrazione SIP). È possibile configurare tale opzione in uno dei due modi seguenti:

  - Configurare il server DHCP nel sito di succursale per rispondere alle query DHCP 120, che restituiscono il nome di dominio completo del servizio di registrazione nel Survivable Branch Appliance o Survivable Branch Server.

  - Abilitare il protocollo DHCP di Lync Server. Quando questa opzione è attivata, il servizio di registrazione di Lync Server risponde a query DHCP Option 120. Si noti che la funzione di registrazione risponde solo alle query DHCP con l'opzione 120.

Nei siti di succursale di grandi dimensioni dotati di più subnet, per inoltrare query DHCP 120 al server DHCP (configurazione 1) o alla funzione di registrazione (configurazione 2), è inoltre necessario abilitare gli agenti di inoltro DHCP.

Infine, gli utenti dei siti di succursale devono essere configurati per VoIP aziendale e provisionati con un endpoint di comunicazioni unificate appropriato.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisiti per Survivable Branch Server

I requisiti per i Survivable Branch Server sono gli stessi dei requisiti per un front end server. Per informazioni dettagliate, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisiti per distribuzioni di siti di succursale Lync Server in scala intera

Per informazioni dettagliate, vedere [Determining Your Infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

