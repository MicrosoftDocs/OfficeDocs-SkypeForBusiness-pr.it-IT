---
title: 'Lync Server 2013: creare o modificare un criterio di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898ffb4473fadd4470ef7e1559fa3cc0c54185c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Creare o modificare criteri per i servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-07_

Seguire questa procedura per creare criteri di conferenza a livello di utente o a livello di sito. Per informazioni dettagliate su come assegnare un criterio a livello di utente a un utente, vedere [assegnare criteri di conferenza per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Per un elenco di tutte le impostazioni dei criteri di conferenza disponibili, vedere informazioni di [riferimento sulle impostazioni per i criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>Per creare un nuovo criterio per un utente o un sito

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.

4.  Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di utente, fare clic su **criteri utente**. In **nome**digitare un nome descrittivo per il criterio in **nuovi criteri di conferenza**.
    
      - Per creare un criterio a livello di sito, fare clic su **criteri sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.
        
        <div>
        

        > [!NOTE]  
        > Il nome del sito diventa il nome del criterio di conferenza e non può essere modificato.

        
        </div>

5.  In **Descrizione**Digitare una descrizione per il criterio.

6.  In **Criteri organizzazione**, in **dimensioni massime riunione**, digitare il numero massimo di utenti che si vuole consentire a una riunione. Per impostazione predefinita, la dimensione massima della riunione è 250.

7.  Per impedire agli utenti di invitare utenti anonimi alle riunioni, deselezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** . Gli utenti anonimi sono utenti che non hanno credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati. Per impostazione predefinita, gli utenti possono invitare utenti anonimi alle riunioni.

8.  In **registrazione**eseguire una delle operazioni seguenti:
    
      - Per impedire ai partecipanti di registrare riunioni, fare clic su **nessuno**. Questa è l'impostazione predefinita.
    
      - Per consentire ai partecipanti di registrare riunioni, fare clic su **Abilita registrazione**.

9.  Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di registrare** . Il valore predefinito è impedire ai partecipanti esterni di registrare riunioni.

10. In **audio/video**eseguire una delle operazioni seguenti:
    
      - Per evitare l'uso di audio e video, fare clic su **nessuno**.
    
      - Per consentire l'uso di audio ma non video, fare clic su **Abilita audio IP**.
    
      - Per consentire l'uso di audio e video, fare clic su **Abilita audio/video IP**. Questa è l'impostazione predefinita.

11. Se si è scelto di consentire l'uso di audio in **audio/video**, eseguire le operazioni seguenti:
    
      - Per impedire agli utenti di partecipare alla riunione effettuando la chiamata, deselezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** . Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).
    
      - Se si consente agli utenti di accedere alle riunioni e si vuole consentire agli utenti non autenticati (anonimi) di partecipare a una riunione con chiamate in uscita, selezionare la casella **di controllo Consenti ai partecipanti anonimi di** effettuare la chiamata in uscita. Con la chiamata in uscita, il server della conferenza chiama l'utente e l'utente risponde al telefono per partecipare alla riunione. Per impostazione predefinita, gli utenti anonimi non possono partecipare a una riunione tramite chiamata in uscita.

12. Se si è scelto di consentire l'uso di video in **audio/video**, selezionare **Consenti più flussi video** .

13. In **collaborazione con i dati**eseguire una delle operazioni seguenti:
    
      - Per impedire la collaborazione con i dati, fare clic su **nessuno**.
    
      - Per consentire la collaborazione con i dati, fare clic su **Abilita collaborazione dati**. Questa è l'impostazione predefinita.

14. Se si è scelto di consentire la collaborazione ai dati in collaborazione con i **dati**, eseguire le operazioni seguenti:
    
      - Per impedire i download esterni, deselezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di scaricare contenuto** . Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.
    
      - Per impedire i trasferimenti di file, deselezionare la casella **di controllo Consenti ai partecipanti di trasferire file** . Per impostazione predefinita, gli utenti possono trasferire file.
    
      - Per evitare l'uso di annotazioni, deselezionare la casella di controllo **Abilita annotazioni** . Per l'uso delle annotazioni nelle presentazioni di PowerPoint frammentate, deselezionare l' **Abilitazione delle annotazioni di PowerPoint**. Per impostazione predefinita, le annotazioni sono consentite.
    
      - Per evitare l'uso dei sondaggi, deselezionare la casella di controllo **Abilita sondaggi** . Per impostazione predefinita, i sondaggi sono consentiti.

15. In **condivisione applicazioni**eseguire una delle operazioni seguenti:
    
      - Per impedire l'uso della condivisione delle applicazioni, fare clic su **Disattiva condivisione applicazioni**.
    
      - Per consentire l'uso della condivisione delle applicazioni, fare clic su **Abilita condivisione applicazioni**. Questa è l'impostazione predefinita.

16. Se si è scelto di consentire la condivisione delle applicazioni nella **condivisione delle applicazioni**, eseguire le operazioni seguenti:
    
      - Per evitare che i partecipanti alla riunione prendano il controllo della condivisione delle applicazioni, deselezionare la casella **di controllo Consenti ai partecipanti di assumere controlli** . Per impostazione predefinita, i partecipanti possono assumere il controllo della condivisione delle applicazioni.
    
      - Se si è scelto di consentire ai partecipanti alla riunione di assumere il controllo della condivisione delle applicazioni, selezionare la casella di controllo **Consenti ai partecipanti federati e anonimi di assumere controlli** per consentire agli utenti esterni di assumere il controllo della condivisione delle applicazioni. Per impostazione predefinita, gli utenti esterni non possono assumere il controllo della condivisione delle applicazioni.

17. In **criteri partecipante**eseguire una delle operazioni seguenti:
    
      - Per impedire sia la condivisione delle applicazioni che la condivisione desktop, fare clic su **Disattiva condivisione applicazioni e desktop**.
    
      - Per consentire la condivisione delle applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.
    
      - Per consentire la condivisione delle applicazioni e la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**. Questa è l'impostazione predefinita.

18. Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento file peer-to-** peer. Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.

19. Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Abilita registrazione peer-to-peer** . Per impostazione predefinita, la registrazione peer-to-peer non è consentita.

20. Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella **di controllo Consenti ai partecipanti di partecipare con più flussi video** . Per impostazione predefinita, sono consentiti più flussi video.

21. Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>Per modificare un criterio di un utente o di un sito esistente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.

4.  Nell'elenco dei criteri di conferenza fare clic sul criterio che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica criteri di conferenza**modificare le impostazioni dei criteri, ad eccezione del nome del criterio, che non può essere modificato.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

