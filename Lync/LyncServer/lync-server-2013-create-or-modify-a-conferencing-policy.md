---
title: 'Lync Server 2013: creare o modificare un criterio conferenza'
description: 'Lync Server 2013: creare o modificare un criterio di conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8715dcde033c4181069f3e30f65b3c29231f51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577982"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Creare o modificare criteri di conferenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-07_

Eseguire la procedura seguente per creare criteri di conferenza a livello di utente o di sito. Per informazioni dettagliate sull'assegnazione di un criterio a livello di utente a un utente, vedere [assegnazione di un criterio di conferenza per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>Per creare nuovi criteri a livello di utente o sito

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.

4.  Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
      - Per creare criteri a livello di utente, fare clic su **Criteri utente**. In **Nuovi criteri conferenza**, in **Nome** digitare un nome descrittivo per il criterio.
    
      - Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare tutto o parte del nome dei sito per cui si desidera creare il criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.
        
        <div>
        

        > [!NOTE]  
        > Il nome del sito diventa il nome del criterio di conferenza e non può essere modificato.

        
        </div>

5.  In **Descrizione** digitare una descrizione per il criterio.

6.  In **Criteri organizzatore**, in **Dimensione massima riunione** digitare il numero massimo di utenti consentiti in una riunione. Per impostazione predefinita, la dimensione massima della riunione è 250 utenti.

7.  Per impedire ai partecipanti di invitare utenti anonimi alle riunioni, deselezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**. Gli utenti anonimi sono utenti che non dispongono di credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati. Per impostazione predefinita, l'invito di utenti anonimi alle riunioni è consentito.

8.  In **Registrazione** eseguire una delle operazioni seguenti:
    
      - Per impedire ai partecipanti di registrare le riunioni, fare clic su **Nessuno**. Questa è l'impostazione predefinita.
    
      - Per consentire ai partecipanti di registrare le riunioni, fare clic su ** Abilita registrazione**.

9.  Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di registrare**. L'impostazione predefinita non consente ai partecipanti esterni di registrare le riunioni.

10. In **Audio/Video** eseguire una delle operazioni seguenti:
    
      - Per impedire l'utilizzo di audio e video, fare clic su **Nessuno**.
    
      - Per consentire l'utilizzo dell'audio, ma non del video, fare clic su **Abilita audio IP**.
    
      - Per consentire l'utilizzo dell'audio e del video, fare clic su **Abilita audio/video IP**. Questa è l'impostazione predefinita.

11. Se si sceglie di consentire l'utilizzo dell'audio in **Audio/Video**, eseguire le operazioni seguenti:
    
      - Per impedire agli utenti di accedere alle riunioni tramite telefono, deselezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono accedere alle riunioni utilizzando la rete PSTN.
    
      - Se si consente agli utenti di accedere alle riunioni tramite telefono e si desidera consentire agli utenti non autenticati (anonimi) di accedere utilizzando chiamate in uscita, selezionare la casella di controllo **Consenti chiamate in uscita ai partecipanti anonimi**. Con le chiamate in uscita il server per conferenze telefona all'utente, il quale accederà alla riunione rispondendo al telefono. Per impostazione predefinita, gli utenti anonimi non possono accedere alle riunioni utilizzando chiamate in uscita.

12. Se si sceglie di consentire l'utilizzo del video in **Audio/Video** selezionare **Consenti più flussi video** .

13. In **Collaborazione dati** eseguire una delle operazioni seguenti:
    
      - Per impedire la collaborazione sui dati, fare clic su **Nessuno**.
    
      - Per consentire la collaborazione sui dati, fare clic su **Abilita collaborazione dati**. Questa è l'impostazione predefinita.

14. Se si è scelto di consentire la collaborazione sui dati in **Collaborazione dati**, eseguire le operazioni seguenti:
    
      - Per impedire i download esterni, deselezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di scaricare contenuto**. Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.
    
      - Per impedire i trasferimenti di file, deselezionare la casella di controllo **Consenti ai partecipanti di trasferire file**. Per impostazione predefinita, gli utenti possono trasferire file.
    
      - Per impedire l'utilizzo delle annotazioni, deselezionare la casella di controllo **Consenti annotazioni**. Per utilizzare le annotazioni in presentazioni di PowerPoint condivise, deselezionare **Abilita annotazioni di PowerPoint**. Per impostazione predefinita, le annotazioni sono consentite.
    
      - Per impedire l'utilizzo dei sondaggi, deselezionare la casella di controllo **Consenti sondaggi**. Per impostazione predefinita, i sondaggi sono consentiti.

15. In **Condivisione applicazioni** eseguire una delle operazioni seguenti:
    
      - Per impedire l'utilizzo della condivisione applicazioni, fare clic su **Disabilita condivisione applicazioni**.
    
      - Per consentire l'utilizzo della condivisione applicazioni, fare clic su **Abilita condivisione applicazioni**. Questa è l'impostazione predefinita.

16. Se si è scelto di consentire la condivisione applicazioni in **Condivisione applicazioni**, eseguire le operazioni seguenti:
    
      - Per impedire ai partecipanti della riunione di assumere il controllo della condivisione applicazioni, deselezionare la casella di controllo **Consenti ai partecipanti di assumere il controllo**. Per impostazione predefinita, i partecipanti possono assumere il controllo.
    
      - Se si è scelto di consentire ai partecipanti di assumere il controllo della condivisione applicazioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di assumere il controllo** per consentire agli utenti esterni di assumere il controllo della condivisione applicazioni. Per impostazione predefinita, gli utenti esterni non possono assumere il controllo.

17. In **Criteri partecipante** eseguire una delle operazioni seguenti:
    
      - Per impedire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Disabilita condivisione applicazioni e desktop**.
    
      - Per consentire la condivisione applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.
    
      - Per consentire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**.

18. Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento di file tramite peer-to-peer**. Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.

19. Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Consenti registrazione peer-to-peer**. Per impostazione predefinita, la registrazione peer-to-peer non è consentita.

20. Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella di controllo **Consenti ai partecipanti di unirsi con più flussi video**. Per impostazione predefinita sono consentiti più flussi video.

21. Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>Per modificare criteri utente o sito esistenti

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.

4.  Nell'elenco dei criteri per conferenza fare clic sui criteri che si desidera modificare, fare clic su **Modifica ** e quindi su **Mostra dettagli**.

5.  In **Modifica criteri conferenza** modificare qualsiasi impostazione dei criteri ad eccezione del nome, che non può essere modificato.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

