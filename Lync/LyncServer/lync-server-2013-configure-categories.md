---
title: 'Lync Server 2013: Configurare le categorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf7b7b3ceb24e3b5bffb307cdde048e7a0cabb8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurare le categorie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione **categoria** della pagina della **chat persistente** per configurare le categorie. Una categoria di chat room persistente è una struttura logica per l'organizzazione di chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso (ACL) per controllare gli utenti e i gruppi di utenti che possono creare o unirsi alle chat room. È possibile usare le categorie per applicare ethical wall tra diverse suddivisioni delle organizzazioni.

Le categorie di chat room possono contenere chat room, ma non altre categorie. Ogni categoria descrive il relativo contenuto con metadati, come Name e Description. La categoria presenta inoltre proprietà che possono essere impostate per controllare il comportamento delle chat room ad essa appartenenti, ad esempio se consentono Invitations o File Uploads oppure contengono Chat History.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.

2.  Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È anche possibile usare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.

4.  Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.

5.  In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server di chat persistente usato dalla chat persistente (client) per identificare a quale pool appartiene la categoria. Una categoria può appartenere a un solo pool di server di chat persistente e non può essere spostata in un'altra o condivisa con un altro pool.

6.  In **Nuova categoria** eseguire le operazioni seguenti:
    
    1.  In **Nome** specificare un nome per la nuova categoria di chat.
    
    2.  In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
    3.  Per controllare se gli inviti possono essere abilitati per le chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita invito** . Se selezionata, le camere di questa categoria possono avere inviti o disattivarli; Se deselezionata, le camere di questa categoria non possono avere inviti. Se una sala contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.
    
    4.  Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che usano Office Communications Server 2007&nbsp;R2 Group Chat Server o Lync Server 2010, Group Chat possono pubblicare file in una sala. Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.

        
        </div>
    
    5.  Per controllare la cronologia chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat** . Se selezionata, le chat room diventano permanenti; in caso contrario, i messaggi di chat non vengono mantenuti. Se è abilitata la conformità, le chat room verranno salvate in conformità, ma gli utenti non potranno accedere ai messaggi meno recenti. Questa opzione può essere usata per le sale designate per le collaborazioni ad hoc in tempo reale che non richiedono la cronologia della chat per essere rese persistenti.

7.  In **Modifica categoria** eseguire le operazioni seguenti:
    
      - In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
      - In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri negati dalla sala.
    
      - In **appartenenza**, nella sezione **Creators** , aggiungere o rimuovere utenti e altre entità Active Directory associate agli autori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.

8.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

