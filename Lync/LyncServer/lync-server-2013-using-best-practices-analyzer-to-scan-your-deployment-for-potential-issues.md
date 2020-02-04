---
title: Uso di Best Practices Analyzer per analizzare la distribuzione per potenziali problemi
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
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Uso di Best Practices Analyzer per analizzare la distribuzione di Lync Server 2013 per potenziali problemi

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Per eseguire un'analisi di Best Practices Analyzer, è necessario specificare quanto segue:

  - **Credenziali**   per eseguire un'analisi, è necessario accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale. Inoltre, è necessario accedere con un account utente che disponga dei diritti utente e delle autorizzazioni necessarie per eseguire le analisi appropriate oppure specificare le credenziali con i diritti utente e le autorizzazioni appropriate quando si esegue Best Practices Analyzer. Per informazioni dettagliate, vedere [appartenenze ai gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Ambito della scansione**   per specificare l'ambito della scansione, selezionare le categorie e i server che si desidera analizzare. È possibile selezionare tutte le categorie, una o più categorie o uno o più server all'interno di una specifica categoria nell'ambiente Lync Server.

  - **Tipo di analisi**   attualmente, l'analisi dell'integrità è l'unico tipo di analisi disponibile (selezionato per impostazione predefinita). L'analisi dell'integrità consente di generare un report che include errori, avvisi e altre informazioni per tutti i server specificati nell'ambito.

  - **** Le opzioni di velocità della rete di velocità della rete includono la LAN veloce (100 Mbps o più), la LAN (10 Mbps), la WAN veloce (1,5 Mbps) o WAN (64 Kbps).    Il tempo stimato per completare l'analisi si basa su questa impostazione. Questa impostazione viene usata anche per impostare il periodo di timeout. Durante l'analisi, l'analizzatore delle procedure consigliate attende una risposta da un server per un determinato periodo di tempo. Se non riceve una risposta entro il periodo di timeout specificato, si sposta sul server successivo nell'analisi. Nelle reti più lente, il periodo di timeout specificato è più lungo per tenere conto delle latenze di rete più lunghe. Ti consigliamo di selezionare il collegamento più lento nella topologia per questo parametro in modo che lo strumento non si esprima troppo rapidamente.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Per analizzare la distribuzione di Lync Server 2013

1.  Accedere a un computer in cui è installato Best Practices Analyzer utilizzando un account membro del gruppo Administrators locale e che disponga di altri diritti utente e autorizzazioni necessari.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.

3.  Nella schermata **iniziale** fare clic su **Seleziona opzioni per una nuova analisi**.

4.  Nella pagina **Connetti a Active Directory** verificare il nome specificato in **Active Directory Server**e quindi eseguire una delle operazioni seguenti:
    
      - Per eseguire un'analisi usando le credenziali usate per accedere al computer, fare clic su **Connetti al server Active Directory**.
    
      - Per specificare credenziali diverse che si desidera utilizzare per servizi di dominio Active Directory, Edge Server o Exchange Server, fare clic su **Mostra opzioni di accesso avanzate**, selezionare ogni casella di controllo per cui sono necessarie credenziali separate, specificare le credenziali per ogni casella di controllo selezionata e quindi fare clic su **Connetti al server di Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Prima di iniziare la scansione, Best Practices Analyzer esegue un controllo della rete e delle autorizzazioni per verificare che le credenziali dell'account specificato siano valide e che Best Practices Analyzer possa connettersi a servizi di dominio Active Directory. Se lo strumento è in uso in un server del gruppo di lavoro, lo strumento verifica anche che possa connettersi a Edge Server nella rete perimetrale (ovvero, se sono inclusi nella scansione).

    
    </div>

5.  Nella pagina **Avvia una nuova analisi delle procedure consigliate** selezionare le opzioni che si desidera includere nella scansione, specificare la velocità di rete e quindi fare clic su **Avvia analisi**.

6.  Nella pagina **analisi completata** fare clic su **Visualizza un report di questa analisi delle procedure consigliate**.

7.  Nella pagina **Visualizza report procedure consigliate** eseguire una delle operazioni seguenti:
    
      - Per visualizzare i report in un elenco organizzato dal componente server, fare clic su **rapporti elenco**e quindi fare clic sulla scheda **tutti i problemi** o sulla scheda **elementi informativi** .
    
      - Per visualizzare i report come elenco gerarchico organizzato in base a tipi di risultati, fare clic su **report albero**e quindi fare clic sulla scheda **visualizzazione dettagliata** o sulla scheda **visualizzazione Riepilogo** .
    
      - Per visualizzare altri report, fare clic su **altri report**.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sui report di analizzatore delle procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">visualizzazione e utilizzo dei report creati da Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati dall'analizzatore delle procedure consigliate in Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

