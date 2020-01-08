---
title: 'Lync Server 2013: Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Seguire questa procedura se si vuole creare o modificare un numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.

<div>


> [!IMPORTANT]  
> Prima di creare un nuovo numero di accesso per la chiamata in ingresso, è necessario impostare un'area di conferenza telefonica con accesso esterno nel dial plan associato al nuovo numero di Access per la chiamata in ingresso. Più piani di chiamata possono usare la stessa area geografica.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>Per creare o modificare un numero di accesso esterno

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di conferenza e quindi su **numero di accesso** **esterno** .

4.  Nella pagina **numero di accesso** esterno effettuare una delle operazioni seguenti:
    
      - Fare clic su **nuovo** per aprire il **nuovo numero di accesso**esterno.
    
      - Fare clic su uno dei numeri di accesso per la chiamata in ingresso nell'elenco, fare clic su **modifica**e quindi su **Mostra dettagli**.
        
        <div>
        

        > [!NOTE]  
        > L'uso del campo di ricerca per cercare il contenuto di una colonna nell'elenco dei numeri di accesso per la chiamata in ingresso potrebbe non restituire i risultati previsti. Ordinare invece l'elenco in base alla colonna di interesse per identificare il numero di accesso esterno che si vuole visualizzare o modificare.

        
        </div>

5.  In **numero di visualizzazione**Digitare il numero di telefono che gli utenti del telefono PSTN (Public Switched Telephone Network) Dial per partecipare a una conferenza.
    
    <div>
    

    > [!NOTE]  
    > Questo numero viene visualizzato negli inviti alle riunioni e nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.

    
    </div>

6.  In **nome visualizzato**Digitare una descrizione per il numero di accesso esterno. Questo è il nome associato al numero di accesso esterno nei risultati della ricerca in Lync.
    
    <div>
    

    > [!NOTE]  
    > Questo nome viene visualizzato nel client quando un utente chiama il numero di accesso.

    
    </div>

7.  In **URI di linea**Digitare il numero e. 164 del numero di accesso esterno in formato Tel URI, incluso il simbolo + prima del numero ed escludendo gli spazi. Ad esempio, Tel: + 14255550200.
    
    <div>
    

    > [!NOTE]  
    > Lo stesso URI di linea non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica in ingresso.

    
    </div>

8.  In **URI SIP**eseguire le operazioni seguenti:
    
      - Nella casella di testo digitare un URI SIP univoco per questo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. Questo URI SIP viene visualizzato in varie posizioni, inclusi, ma non solo, i messaggi di notifica delle chiamate e le versioni precedenti dei client Communicator.
        
        <div>
        

        > [!NOTE]  
        > Lo stesso URI SIP non può essere riutilizzato da un altro numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso. L'URI SIP non può essere modificato dopo la creazione del numero di accesso. L'unico modo per modificare l'URI SIP consiste nell'eliminare e ricreare il numero di accesso.

        
        </div>
    
      - Nella casella di riepilogo a discesa fare clic sul dominio dell'applicazione operatore di conferenza che supporta questo numero di accesso esterno.

9.  In **pool**fare clic sul pool in cui è in esecuzione l'istanza di operatore conferenza che supporta questo numero di accesso esterno.
    
    <div>
    

    > [!NOTE]  
    > Se è necessario modificare il pool dopo la creazione del numero di accesso, è necessario usare il cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> oppure eliminare e ricreare il numero di accesso.

    
    </div>

10. In **lingua principale**fare clic sulla lingua in cui vengono riprodotti le richieste per questo numero di accesso esterno.
    
    <div>
    

    > [!NOTE]  
    > La lingua principale è la lingua che l'operatore di conferenza USA per rispondere alla chiamata. Le lingue supportate vengono visualizzate accanto a ogni numero di telefono di Access nella pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.

    
    </div>

11. Opzionale In **lingue secondarie (massimo quattro)** fare clic su **Aggiungi**, selezionare una o più lingue aggiuntive che si desidera supportare per i chiamanti per il numero di accesso esterno e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > È possibile scegliere fino a quattro lingue secondarie per ogni numero di accesso esterno. Gli utenti possono selezionare una lingua secondaria prima di immettere l'ID conferenza quando effettuano la chiamata a una conferenza.

    
    </div>

12. Per aggiungere un'area geografica per il numero di accesso esterno, fare clic su **Aggiungi**in **aree geografiche associate**, fare clic su una o più aree geografiche associate ai dial plan per questo numero di accesso esterno e quindi fare clic su **OK**.

13. Per eliminare un'area dal numero di accesso esterno, in **aree geografiche associate**fare clic sull'area che si vuole eliminare e quindi fare clic su **Rimuovi**.

14. Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

