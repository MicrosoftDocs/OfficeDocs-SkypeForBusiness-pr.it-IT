---
title: 'Lync Server 2013: creare o modificare un numero di accesso per le conferenze telefoniche con chiamata in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f684166c7a33f092ee9d7a00eb9582cb70e2606
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Creare o modificare un numero di accesso per le conferenze telefoniche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Eseguire questa procedura se si desidera creare o modificare un numero di accesso per partecipare a una conferenza telefonica con accesso esterno.

<div>


> [!IMPORTANT]  
> Prima di creare un nuovo numero di accesso esterno, è necessario impostare per tale numero un'area di conferenza telefonica con accesso esterno associata al dial plan. Più dial plan possono utilizzare la stessa area.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Per creare o modificare un numero di accesso esterno

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Numero di accesso esterno**.

4.  Nella pagina **Numero di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Fare clic su **Nuovo** per aprire **Nuovo numero di accesso esterno**.
    
      - Fare clic su uno dei numeri di accesso esterno nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.
        
        <div>
        

        > [!NOTE]  
        > Se si utilizza il campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso esterno, i risultati ottenuti potrebbero non essere quelli previsti. Ordinare invece l'elenco in base alla colonna a cui si è interessati per identificare il numero di accesso esterno da visualizzare o modificare.

        
        </div>

5.  In **Numero visualizzato** digitare il numero di telefono che gli utenti della rete PSTN (Public Switched Telephone Network) devono comporre per partecipare a una conferenza.
    
    <div>
    

    > [!NOTE]  
    > Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web Impostazioni conferenza telefonica con accesso esterno.

    
    </div>

6.  In **Nome visualizzato** digitare una descrizione per il numero di accesso esterno. Si tratta del nome associato al numero di accesso esterno nei risultati della ricerca di Lync.
    
    <div>
    

    > [!NOTE]  
    > Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.

    
    </div>

7.  In **URI linea** digitare il numero E.164 del numero di accesso esterno nel formato URI TEL, preceduto dal simbolo + e senza utilizzare spazi. Ad esempio, tel:+14255550200.
    
    <div>
    

    > [!NOTE]  
    > Non è possibile riutilizzare lo stesso URI linea per un altro numero di accesso per conferenze con accesso esterno.

    
    </div>

8.  In **URI SIP** eseguire le operazioni seguenti:
    
      - Nella casella di testo digitare un URI SIP univoco per il numero di accesso per conferenze con accesso esterno. Questo URI SIP viene visualizzato in diverse posizioni, tra cui, ma non solo, i messaggi di notifica di chiamata e le versioni precedenti dei client Communicator.
        
        <div>
        

        > [!NOTE]  
        > Non è possibile riutilizzare lo stesso URI SIP per un altro numero di accesso per conferenze con accesso esterno. L'URI SIP non può essere modificato dopo che il numero di accesso è stato creato. L'unico modo per modificare l'URI SIP è quello di eliminare e ricreare il numero di accesso.

        
        </div>
    
      - Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione Operatore Conferenza che supporta il numero di accesso esterno.

9.  In **Pool** fare clic sul pool che esegue l'istanza di Operatore Conferenza che supporta il numero di accesso esterno.
    
    <div>
    

    > [!NOTE]  
    > Se è necessario modificare il pool dopo avere creato il numero di accesso, utilizzare il cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> oppure eliminare e ricreare il numero di accesso.

    
    </div>

10. In **Lingua principale** fare clic sulla lingua in cui verranno riprodotte le richieste per il numero di accesso esterno.
    
    <div>
    

    > [!NOTE]  
    > La lingua principale è la lingua utilizzata da Operatore Conferenza per rispondere alla chiamata. Le lingue supportate vengono visualizzate insieme a ogni numero di telefono di accesso nella pagina Web Impostazioni conferenza telefonica con accesso esterno.

    
    </div>

11. (Facoltativo) In **Lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti al numero di accesso esterno e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > È possibile selezionare fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando chiamano per partecipare a una conferenza.

    
    </div>

12. Per aggiungere un'area per il numero di accesso esterno, in **aree associate**fare clic su **Aggiungi**, fare clic su una o più aree associate ai dial plan per il numero di accesso esterno e quindi fare clic su **OK**.

13. Per eliminare un'area dal numero di accesso esterno, in **Aree associate** fare clic sull'area desiderata e quindi su **Rimuovi**.

14. Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

