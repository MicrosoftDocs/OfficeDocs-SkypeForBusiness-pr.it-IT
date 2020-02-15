---
title: Utilizzo di Best Practices Analyzer per analizzare la distribuzione per individuare potenziali problemi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afda261fc3e57750afaabbf349eb31631adea275
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Utilizzo di Best Practices Analyzer per analizzare la distribuzione di Lync Server 2013 per potenziali problemi

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

Per eseguire un'analisi di Best Practices Analyzer è necessario specificare quanto segue:

  - **Credenziali**   per l'esecuzione di un'analisi, è necessario accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale. L'account deve inoltre disporre dei diritti e delle autorizzazioni utente richieste per l'esecuzione di Best Practices Analyzer. Per informazioni dettagliate, vedere [appartenenza a gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Ambito di analisi**   per specificare l'ambito dell'analisi, selezionare le categorie e i server che si desidera analizzare. È possibile selezionare tutte le categorie, una o più categorie o uno o più server all'interno di una categoria specifica nell'ambiente Lync Server.

  - **Tipo di analisi**   attualmente, la verifica dell'integrità è l'unico tipo di analisi disponibile (selezionata per impostazione predefinita). Quest'analisi genera un rapporto che include errori, avvisi e altre informazioni relative a tutti i server specificati nell'ambito.

  - ****   Le opzioni di velocità della rete Speed Network includono Fast LAN (100 Mbps o più), LAN (10 Mbps), Fast WAN (1,5 Mbps) o WAN (64 Kbps). Il tempo stimato per il completamento dell'analisi si basa su questa impostazione. Questa impostazione viene utilizzata anche per impostare il periodo di timeout. Durante l'analisi, l'Analizzatore procedure consigliate attende una risposta da un server per un determinato periodo di tempo. Se non riceve una risposta entro il periodo di timeout specificato, si sposta sul server successivo nell'analisi. Nelle reti più lente, il periodo di timeout specificato è più lungo per tenere conto delle latenze della rete più lunghe. È consigliabile selezionare il collegamento più lento nella topologia per questo parametro, in modo che lo strumento non venga disgiunto troppo rapidamente.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Per analizzare la distribuzione di Lync Server 2013

1.  Accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale e che disponga di tutti i diritti e le autorizzazioni necessarie.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.

3.  Nella schermata iniziale**** scegliere **Seleziona le opzioni per una nuova analisi**.

4.  Nella pagina **Connessione a Active Directory** verificare il nome specificato in **Server Active Directory** e quindi eseguire una delle operazioni seguenti:
    
      - Per eseguire un'analisi con le stesse credenziali utilizzate per accedere al computer, fare clic su **Connessione al server Active Directory**.
    
      - Per specificare credenziali diverse da utilizzare per Servizi di dominio Active Directory, server perimetrali o server Exchange, fare clic su **Mostra opzioni di accesso avanzate**, selezionare le caselle di controllo per cui sono necessarie credenziali separate, specificare le credenziali per ogni casella di controllo selezionata e quindi fare clic su **Connessione al server Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Prima di iniziare l'analisi, Best Practices Analyzer esegue un controllo della rete e delle autorizzazioni, per verificare che le credenziali dell'account specificate siano valide e che lo strumento sia in grado connettersi a Servizi di dominio Active Directory. Se lo strumento è in esecuzione in un server Workgroup, verifica inoltre che sia possibile eseguire la connessione ai server perimetrali presenti nella rete perimetrale (se sono inclusi nell'analisi).

    
    </div>

5.  Nella pagina **Avvia una nuova analisi Best Practices** selezionare le opzioni da includere nell'analisi, specificare la velocità di rete e quindi fare clic su **Avvia l'analisi**.

6.  Nella pagina **Analisi completata** fare clic su **Visualizza un rapporto di questa analisi Best Practices**.

7.  Nella pagina **Visualizza rapporto Best Practices** eseguire una delle operazioni seguenti:
    
      - Per visualizzare i rapporti in un elenco organizzato per componente server, fare clic su **Elenca rapporti**, quindi fare clic sulla scheda **Tutti i problemi** o **Elementi informativi**.
    
      - Per visualizzare i rapporti in un elenco gerarchico organizzato per tipo di risultato, fare clic su **Rapporti albero**, quindi fare clic sulla scheda **Visualizzazione Dettagli** o **Visualizzazione riepilogo**.
    
      - Per visualizzare altri rapporti, fare clic su **Altri rapporti**.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sui report Analizzatore procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">viewing and working with Reports created by Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati da Best Practices Analyzer in Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

