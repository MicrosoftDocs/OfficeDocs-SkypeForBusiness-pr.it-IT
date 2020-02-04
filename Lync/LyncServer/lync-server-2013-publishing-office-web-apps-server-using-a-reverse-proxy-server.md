---
title: Pubblicazione di Office Web Apps Server tramite un server proxy inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Pubblicazione di Office Web Apps Server in Lync Server 2013 con un server proxy inverso

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

Se si vuole che gli utenti esterni (ovvero gli utenti che accedono dall'esterno del firewall dell'organizzazione) abbiano accesso alle presentazioni di PowerPoint in Office Web Apps Server, è necessario usare Office Web Apps Server e un server proxy inverso, ad esempio Microsoft Forefront Gateway di gestione delle minacce. Ciò significa anche che dovrai creare e configurare una regola di pubblicazione del sito Web; Questa regola consentirà di garantire agli utenti la possibilità di connettersi al server. Se non è necessario consentire l'accesso a utenti esterni, non è necessario configurare una regola di pubblicazione del sito Web.

Per configurare una regola di pubblicazione del sito Web in Forefront Threat Management Gateway, eseguire la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Forefront TMG**e quindi su **gestione di Forefront TMG**.

2.  In Forefront TMG fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.

3.  Nella pagina **Introduzione** alla nuova regola di pubblicazione Web digitare un nome per la nuova regola nella casella **Nome regola pubblicazione** Web, ad esempio **regola del server di Office Web Apps**, e quindi fare clic su **Avanti**.

4.  Nella pagina **specifica azione regola** selezionare **Consenti** e quindi fare clic su **Avanti**.

5.  Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico** e quindi fare clic su **Avanti**.

6.  Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm** , quindi fare clic su **Avanti**.

7.  Nella pagina **Internal Publishing Details** Digitare il nome di dominio completo del server di Office Web Apps, ad esempio **officewebapps01.contoso.com**, nella casella **Name sito interno** e quindi fare clic su **Avanti**. Il nome immesso nella casella **nome sito interno** deve essere visualizzato nel campo oggetto o nel campo nome alternativo oggetto del certificato assegnato a Office Web Apps Server.

8.  Nella pagina **Dettagli pubblicazione interna** Digitare ** / ** la casella **percorso (facoltativo)** e quindi fare clic su **Avanti**. La sintassi\* //consente di verificare che tutte le cartelle e le sottocartelle per il sito vengano pubblicate.

9.  Nella pagina **Dettagli nome pubblico** selezionare **questo nome di dominio (digitare di seguito)** nell'elenco a discesa **accetta richieste per** e quindi digitare il qualificato per il server Office Web Apps nella casella nome pubblico. Questo nome deve essere il nome usato per accedere al sito Web. Ad esempio, se si accede al sito usando l'URL http://officewebapps01.contoso.com , è necessario immettere **officewebapps01.contoso.com** nella casella **nome pubblico** .

10. Fare clic su **Avanti**.

11. Nella pagina **Seleziona listener Web** fare clic su **nuovo**.

12. Nella creazione guidata nuova definizione listener Web digitare un nome per il nuovo listener Web (ad esempio **SSL**) nella casella **nome listener** Web e quindi fare clic su **Avanti**.

13. Nella pagina **sicurezza connessione client** selezionare **Richiedi connessioni protette SSL con i client** e quindi fare clic su **Avanti**.

14. Nella pagina **indirizzi IP del listener Web** selezionare **esterno**, selezionare **interno**e quindi fare clic su **Avanti**.

15. Nella pagina **certificati SSL listener** selezionare **Usa un singolo certificato per il listener Web** e quindi fare clic su **Seleziona certificato**.

16. Nella finestra di dialogo **Seleziona certificato** selezionare il certificato da usare per il listener Web e quindi fare clic su **Seleziona**.

17. Nella pagina **certificati SSL listener** fare clic su **Avanti**.

18. Nella pagina **impostazioni di autenticazione** selezionare **Nessuna autenticazione** dall'elenco **a discesa selezionare il modo in cui i client impareranno le credenziali per i clienti di Forefront TMG** e quindi fare clic su **Avanti**.

19. Nella pagina **Impostazioni Single Sign-in** fare clic su **Avanti**.

20. Nella pagina **completamento della creazione guidata nuovo listener Web** esaminare il riepilogo delle opzioni di configurazione effettuate. Una volta pronti, fare clic su **fine**.

21. Nella pagina **Seleziona listener Web** fare clic su **Avanti**.

22. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire** l'autenticazione direttamente dal **selezionare il metodo usato da Forefront TMG per eseguire l'autenticazione nell'elenco a discesa del server Web pubblicato** e quindi fare clic su **Avanti**.

23. Nella pagina **set di utenti** verificare che siano elencati i set di utenti appropriati. Per impostazione predefinita, questo è il set di **utenti all** Users. Fare clic su **Aggiungi** per aggiungere altri set di utenti che possono essere stati definiti. Al termine, fare clic su **Avanti**.

24. Nella pagina **completamento della nuova creazione guidata regola Web Publishing** fare clic su **fine**.

Tieni presente che fare clic su **fine** non significa che hai completato il processo; Questo significa che non si applica automaticamente e Abilita la nuova regola. Sarà invece necessario fare clic sul pulsante **applica** che verrà visualizzato nell'interfaccia utente di Forefront TMG. Quando si fa clic su **applica** viene visualizzata la finestra di dialogo **Descrizione modifica configurazione** . Fare clic su **applica** nella finestra di dialogo per abilitare la nuova regola di pubblicazione.

Dopo l'applicazione della nuova regola, sarà necessario apportare alcune modifiche minime alla regola per verificare che gli utenti possano usare le nuove funzionalità di presentazione di PowerPoint. Per eseguire questa operazione, eseguire la procedura seguente:

1.  In Forefront TMG fare clic con il pulsante destro del mouse sul nome della nuova regola di pubblicazione e quindi scegliere **Proprietà**.

2.  Nella scheda a della finestra **di** dialogo **Proprietà** selezionare l'opzione **Inoltra l'intestazione host originale invece di quella effettiva**.

3.  Nella scheda **traffico** fare clic su **filtro** e quindi su **configura http**.

4.  Nella finestra di dialogo **configurazione dei criteri HTTP per la regola** deselezionare la casella di controllo **Verifica normalizzazione** e quindi fare clic su **OK**.

5.  Nella finestra di dialogo **Proprietà** fare clic su **OK**.

6.  In Forefront TMG fare clic su **applica** per abilitare le modifiche. Quando viene visualizzata la finestra di dialogo **Descrizione modifica configurazione** , fare clic su **applica**.

Dopo aver completato l'installazione, è possibile testare il server di Office Web Apps usando le procedure descritte nell'argomento [convalida della configurazione di Office Web Apps Server in Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

