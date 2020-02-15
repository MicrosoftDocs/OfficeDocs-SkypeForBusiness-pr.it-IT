---
title: 'Lync Server 2013: configurare le categorie'
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
ms.openlocfilehash: a2092614abd250c96f8bc6ef20969635ca229756
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurare le categorie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la sezione **categoria** della pagina **chat persistente** per configurare le categorie. Una categoria di chat persistente è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso per il controllo degli utenti e dei gruppi di utenti che possono creare chat room o prendervi parte. Le categorie possono essere usate per applicare gli ethical wall tra le varie suddivisioni all'interno delle organizzazioni.

Le categorie di chat room possono contenere chat room, ma non altre categorie. Ogni categoria descrive il relativo contenuto con metadati, come Nome e Descrizione. La categoria presenta inoltre proprietà che possono essere impostate per controllare il comportamento delle chat room ad essa appartenenti, ad esempio se consentono Inviti o Caricamenti file oppure contengono Cronologia chat.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato dall'elenco a discesa.

4.  Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.

5.  In **Seleziona un servizio**selezionare il servizio corrispondente al pool di server Chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server Chat persistente utilizzato dal client per identificare il pool a cui appartiene la categoria. Una categoria può appartenere a un solo pool di server Chat persistente e non può essere spostata in un'altra o condivisa con un altro pool.

6.  In **Nuova categoria** eseguire le operazioni seguenti:
    
    1.  In **Nome** specificare un nome per la nuova categoria di chat.
    
    2.  In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
    3.  Per controllare l'abilitazione di inviti nelle chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita inviti**. Se l'opzione viene selezionata, le chat di questa categoria possono avere inviti attivati o disattivati; se invece viene deselezionata, alle chat di questa categoria non è consentito avere inviti. Se una chat room contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.
    
    4.  Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che utilizzano Office Communications Server 2007&nbsp;R2 Group Chat Server o Lync Server 2010, Group Chat possono inserire file in una sala. Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.

        
        </div>
    
    5.  Per controllare la cronologia della chat, seleziona o deseleziona la casella di controllo **Abilita cronologia chat** . Se la casella è selezionata, le chat room diventano persistenti, in caso contrario i messaggi delle chat non diventano persistenti. Se è abilitata la conformità, le chat room verranno salvate nella conformità, ma gli utenti non potranno accedere ai messaggi datati. Questa opzione può essere usata per le chat designate per collaborazioni ad hoc in tempo reale che non richiedono la persistenza della cronologia della chat.

7.  In **Modifica categoria** eseguire le operazioni seguenti:
    
      - In **appartenenza**, nella sezione **consentito membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
      - In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri che vengono negati dalla sala.
    
      - In **appartenenza**, nella sezione **creatori** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai creatori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.

8.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

