---
title: Requisiti per le conferenze telefoniche con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 944aaf06ce81e5ba326841f6abe91614cdffd134
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498913"
---
# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Prima di avviare il processo di distribuzione di Lync Server 2013, è necessario pianificare le operazioni seguenti:

  - La configurazione da utilizzare per la connessione alla rete PSTN (Public Switched Telephone Network)

  - La strategia per l'assegnazione delle aree di conferenza telefonica con accesso esterno ai numeri di chiamata in ingresso

  - La strategia per la creazione di directory conferenze

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Pianificazione della connettività PSTN con accesso esterno

Le conferenze telefoniche con accesso esterno richiedono almeno un Mediation Server e almeno un gateway PSTN.

È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale. In un sito centrale è possibile collocare un Mediation Server in un pool Front end o in un server Standard Edition oppure è possibile distribuirlo in un server autonomo o in un pool. In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente del Survivable Branch Appliance.

È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale. In un sito di succursale, il gateway PSTN può essere autonomo o come componente del Survivable Branch Appliance.

<div>


> [!NOTE]  
> Le conferenze telefoniche con accesso esterno non utilizzano il bypass multimediale perché A/V Conferencing Server non supporta il bypass multimediale.



</div>

Per informazioni dettagliate sulla pianificazione della configurazione per il Mediation Server e i gateway PSTN per le conferenze telefoniche con accesso esterno, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Pianificazione delle aree di conferenza telefonica con accesso esterno

Durante la configurazione della chiamata in ingresso, è possibile creare numeri di accesso esterno e dial plan. I dial plan sono insiemi di regole di normalizzazione che specificano il numero e il modello di cifre di un numero di telefono e traducono il numero di telefono nel formato E. 164 standard per il routing delle chiamate. Le conferenze telefoniche con accesso esterno sono i numeri che i partecipanti chiamano per partecipare a una conferenza.

Ogni numero di accesso per le conferenze telefoniche in ingresso deve essere associato ad almeno un dial plan. Le aree di conferenza telefonica con accesso esterno associano un numero di telefono per le conferenze telefoniche con dial plan. Quando si configura un dial plan, è necessario specificare l'area di conferenza telefonica con accesso esterno che si applica al dial plan. Quando si crea il numero di accesso esterno, si selezionano le aree geografiche che associano il numero di accesso ai dial plan corretti.

Quando si crea un dial plan, è necessario specificare l'ambito del dial plan: ambito utente, ambito del pool o ambito del sito. A ogni utente viene assegnato il dial plan dall'ambito più stretto applicato all'utente. Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se si applica. Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool. Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito. Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale.

Prima di configurare i dial plan, è importante pianificare la modalità di denominazione e l'utilizzo delle aree geografiche. Le considerazioni seguenti sono valide per le aree di conferenza telefonica con accesso esterno:

  - Una regione è in genere un'area geografica associata a un ufficio o a un gruppo di uffici.

  - Le lingue sono associate ai numeri di accesso esterno. Se si supportano aree geografiche con più lingue, è necessario decidere in che modo si desidera definire le aree per il supporto di più lingue. Ad esempio, è possibile definire più aree in base a una combinazione di geografia e lingua oppure definire una singola area geografica in base alla geografia e disporre di un numero di accesso esterno diverso per ogni lingua.

  - Quando un utente pianifica una riunione, per impostazione predefinita la riunione utilizza l'area specificata dal dial plan dell'utente.

  - Per impostazione predefinita, tutti i numeri di accesso esterno per l'area sono inclusi nell'invito alla riunione.

  - È importante assegnare un nome alle aree geografiche in modo che siano chiaramente riconoscibili. L'utente può utilizzare i nomi delle aree geografiche per modificare l'area di una riunione in modo che i numeri di accesso diversi siano inclusi nell'invito. Quando gli utenti utilizzano Outlook per pianificare una riunione, l'utente utilizza il componente aggiuntivo per riunioni online per Lync 2013 per modificare l'area geografica.

  - Le aree geografiche devono essere progettate in modo che qualsiasi invitato che desidera comporre una conferenza possa visualizzare un numero di accesso locale nell'invito alla conferenza.

  - È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina Impostazioni conferenza telefonica con chiamata in ingresso (e, di conseguenza, nell'ordine in cui vengono visualizzati nell'invito alla conferenza) utilizzando i cmdlet di Lync Server Management Shell.

  - Qualsiasi utente da qualsiasi percorso può chiamare qualsiasi numero di accesso esterno per partecipare a una conferenza.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Pianificazione delle directory conferenze

Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Lync 2013 e l'ID conferenza solo numerico utilizzato da un partecipante di conferenze telefoniche con accesso esterno per partecipare alla conferenza. Il formato dell'ID conferenza è il seguente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La creazione di più directory conferenze garantirà che gli ID conferenza rimarranno invariati fino a quando non verrà creata una quantità significativa di conferenze. In un'organizzazione che dispone di un numero tipico di conferenze per utente, si consiglia di creare una directory conferenze per ogni 999 utenti nel pool. Utilizzo di questa guida di riferimento gli ID conferenza possono generalmente essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenze (tra i pool) è superiore a 9, il numero dell'ID conferenza aumenterà per supportare altre conferenze.

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

