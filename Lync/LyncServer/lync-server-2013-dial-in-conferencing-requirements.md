---
title: Requisiti per i servizi di conferenza telefonica con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Prima di avviare il processo di distribuzione di Lync Server 2013 è necessario pianificare le operazioni seguenti:

  - La configurazione da usare per la connessione alla rete PSTN (Public Switched Telephone Network)

  - Strategia per l'assegnazione di aree per i servizi di conferenza telefonica con accesso esterno ai numeri di telefono

  - Strategia per la creazione di directory conferenza

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Pianificazione della connettività PSTN con accesso esterno

I servizi di conferenza telefonica con accesso esterno richiedono almeno un Mediation Server e almeno un gateway PSTN.

È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale. In un sito centrale è possibile collocare un Mediation Server in un pool Front-end o in un server Standard Edition oppure distribuirlo in un server o un pool autonomo. In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente di Survivable Branch Appliance.

È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale. In un sito di succursale il gateway PSTN può essere autonomo o un componente dell'appliance Survivable Branch.

<div>


> [!NOTE]  
> I servizi di conferenza telefonica con accesso esterno non usano il bypass multimediale perché un/V Conferencing Server non supporta il bypass multimediale.



</div>

Per informazioni dettagliate sulla pianificazione della configurazione per Mediation Server e gateway PSTN per i servizi di conferenza telefonica con accesso esterno, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Pianificazione per le aree di conferenza telefonica con accesso esterno

Durante la configurazione della chiamata in ingresso, è possibile creare piani di chiamata e numeri di accesso per i servizi di conferenza telefonica I dial plan sono insiemi di regole di normalizzazione che specificano il numero e il modello di cifre in un numero di telefono e traducono il numero di telefono nel formato standard E. 164 per il routing delle chiamate. I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso sono i numeri che partecipano a una conferenza.

Tutte le conferenze telefoniche con accesso esterno devono essere associate ad almeno un dial plan. Le aree dei servizi di conferenza telefonica con accesso esterno associano un numero di telefono per i servizi di conferenza telefonica con dial plan. Quando si configura un dial plan, si specifica l'area dei servizi di conferenza telefonica con accesso esterno che si applica al dial plan. Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati.

Quando si crea un dial plan, si specifica l'ambito del dial plan: ambito utente, ambito del pool o ambito del sito. A ogni utente viene assegnato il dial plan dall'ambito più ristretto che si applica all'utente. Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se si applica. Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool. Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito. Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale.

Prima di configurare i dial plan, è importante pianificare il nome e l'uso delle aree geografiche. Le considerazioni seguenti si applicano alle aree dei servizi di conferenza telefonica con accesso esterno:

  - In genere un'area geografica è associata a un ufficio o a un gruppo di uffici.

  - Le lingue sono associate ai numeri di accesso per la chiamata in ingresso. Se si supportano aree geografiche con più lingue, è necessario decidere come definire le aree per il supporto di più lingue. Ad esempio, è possibile definire più aree in base a una combinazione di geografia e lingua oppure definire una singola area geografica in base alla geografia e avere un numero di accesso esterno diverso per ogni lingua.

  - Quando un utente pianifica una riunione, per impostazione predefinita la riunione usa l'area specificata dal dial plan dell'utente.

  - Per impostazione predefinita, tutti i numeri di accesso per le connessioni in ingresso per l'area geografica sono inclusi nell'invito alla riunione.

  - È importante assegnare un nome alle aree geografiche in modo che siano chiaramente riconoscibili. L'utente può usare i nomi delle aree geografiche per modificare l'area geografica di una riunione in modo da includere nell'invito diversi numeri di accesso. Quando gli utenti usano Outlook per pianificare una riunione, l'utente usa il componente aggiuntivo riunione online per Lync 2013 per modificare l'area geografica.

  - Le aree geografiche devono essere progettate in modo che tutti gli invitati che desiderano connettersi a una conferenza possano visualizzare un numero di accesso locale nell'invito alla conferenza.

  - È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina delle impostazioni di conferenza telefonica con accesso esterno (e, di conseguenza, nell'ordine in cui vengono visualizzati nell'invito alla conferenza) usando i cmdlet di Lync Server Management Shell.

  - Qualsiasi utente da qualsiasi luogo può chiamare un numero di accesso esterno per partecipare a una conferenza.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Pianificazione per le directory conferenza

Le directory conferenza mantengono un mapping tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Lync 2013 e l'ID conferenza solo numerico usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza. Il formato dell'ID conferenza è il seguente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze. In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool. Uso di questa guida di riferimento gli ID conferenza possono in genere essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, il numero dell'ID conferenza crescerà per supportare altre conferenze.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Componente Mediation Server in Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

