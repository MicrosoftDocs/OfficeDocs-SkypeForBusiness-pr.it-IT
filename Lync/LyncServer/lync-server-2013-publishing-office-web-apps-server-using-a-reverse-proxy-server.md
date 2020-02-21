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
ms.openlocfilehash: e9a2bc53d306b51bd6aa681ccb4aa6747f38eac7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Pubblicazione del server Office Web Apps in Lync Server 2013 utilizzando un server proxy inverso

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

Se si desidera che gli utenti esterni, ovvero gli utenti che eseguono l'accesso dall'esterno del firewall dell'organizzazione, possano accedere alle presentazioni di PowerPoint di Office Web Apps Server, sarà necessario usare Office Web Apps Server e un server proxy inverso come Microsoft Forefront Threat Management Gateway. Questo significa anche che sarà necessario creare e configurare una regola di pubblicazione del sito Web. tale regola consentirà di garantire che gli utenti siano in grado di connettersi al server. Se non è necessario fornire accesso agli utenti esterni, non è necessario configurare una regola di pubblicazione del sito Web.

Per configurare una regola di pubblicazione del sito Web in Forefront Threat Management Gateway, eseguire la procedura seguente:

1.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Forefront TMG** e quindi **Gestione Forefront TMG**.

2.  In Forefront TMG fare clic con il pulsante destro del mouse su **Criterio firewall**, scegliere **Nuovo** e fare clic su **Regola di pubblicazione sito Web**.

3.  Nella pagina iniziale della **Creazione guidata regola di pubblicazione sul Web** digitare un nome per la nuova regola nella casella **Nome regola di pubblicazione sul Web**, ad esempio **Regola Office Web Apps Server**, quindi fare clic su **Avanti**.

4.  Nella pagina **Seleziona azione regola** selezionare **Consenti** e fare clic su **Avanti**.

5.  Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**, quindi fare clic su **Avanti**.

6.  Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**, quindi fare clic su **Avanti**.

7.  Nella pagina **Dettagli pubblicazione interna** digitare il nome di dominio completo del server Office Web Apps, ad esempio **officewebapps01.contoso.com**, nella casella **Nome sito interno**, quindi fare clic su **Avanti**. Il nome immesso nella casella **Nome sito interno** deve comparire nel campo Soggetto e nel campo Nome alternativo soggetto del certificato assegnato a Office Web Apps Server.

8.  Nella pagina **Dettagli pubblicazione interna** Digitare ** / ** la casella **percorso (facoltativo)** e quindi fare clic su **Avanti**. La sintassi\* //consentirà di verificare che vengano pubblicate tutte le cartelle e le sottocartelle del sito.

9.  Nella pagina **Dettagli nome pubblico** selezionare **Questo nome dominio (immettere di seguito)** nell'elenco a discesa **Accetta richieste per**, quindi digitare il nome completo di Office Web Apps Server nella casella Nome pubblico. Questo nome deve corrispondere a quello utilizzato per accedere al sito Web. Ad esempio, se si accede al sito utilizzando l'URL http://officewebapps01.contoso.com , è necessario immettere **officewebapps01.contoso.com** nella casella **nome pubblico** .

10. Fare clic su **Avanti**.

11. Nella pagina **Scegliere Listener Web** fare clic su **Nuovo**.

12. Nella Creazione guidata definizione listener Web digitare un nome per il listener Web, ad esempio **SSL**, nella casella **Nome listener Web** e fare clic su **Avanti**.

13. Nella pagina **Protezione di connessione client** selezionare **Richiedi connessioni SSL protette con i client**, quindi fare clic su **Avanti**.

14. Nella pagina **Indirizzi IP del listener Web** selezionare **Esterno**, selezionare **Interno**, quindi fare clic su **Avanti**.

15. Nella pagina **Certificati SSL listener ** selezionare **Usa un unico certificato per questo listener Web**, quindi fare clic su **Seleziona certificato**.

16. Nella finestra di dialogo **Seleziona certificato** selezionare il certificato da usare per il listener Web e fare clic su **Seleziona**.

17. Nella pagina **Certificati SSL listener** fare clic su **Avanti**.

18. Nella pagina **Impostazione di autenticazione ** selezionare **Nessuna autenticazione** nell'elenco a discesa **Selezionare la modalità in cui i client forniscono le credenziali a Forefront TMG**, quindi fare clic su **Avanti**.

19. Nella pagina **Impostazioni Single Sign-On** fare clic su **Avanti**.

20. Nella pagina **Completamento della Creazione guidata listener Web** rivedere il riepilogo delle scelte di configurazione effettuate. Al termine, fare clic su **Fine**.

21. Nella pagina **Scegliere Listener Web** fare clic su **Avanti**.

22. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente** nell'elenco a discesa **Scegliere il metodo utilizzato da Forefront TMG per autenticare il server Web pubblicato**, quindi fare clic su **Avanti**.

23. Nella pagina **Gruppi di utenti** verificare che siano elencati i gruppi di utenti appropriati. Per impostazione predefinita si tratta del gruppo **Tutti gli utenti**. Per aggiungere altri set di utenti definiti, fare clic su **Aggiungi**. Al termine, fare clic su **Avanti**.

24. Nella pagina finale della **Creazione guidata regola di pubblicazione sul Web** fare clic su **Fine**.

Fare clic su **Fine** non significa che il processo è terminato, ovvero la nuova regola non viene applicata e abilitata automaticamente. A questo scopo sarà necessario fare clic sul pulsante **Applica** nell'interfaccia utente di Forefront TMG. Quando si fa clic su **Applica** viene visualizzata la finestra di dialogo con la**** descrizione della modifica apportata alla configurazione. Per applicare la nuova regola di pubblicazione, fare clic su **Applica** in tale finestra.

Dopo l'applicazione della nuova regola, è necessario apportare alcune modifiche minime alla regola per assicurarsi che gli utenti possano utilizzare le nuove funzionalità di presentazione di PowerPoint. Eseguire la procedura seguente:

1.  In Forefront TMG fare clic con il pulsante destro del mouse sulla nuova regola di pubblicazione e scegliere **Proprietà**.

2.  Nella scheda**A** della finestra di dialogo **Proprietà** selezionare l'opzione **Inoltra l'intestazione host originale e non quella effettiva (nel campo Nome sito interno)**.

3.  Nella scheda **Traffico** fare clic su **Filtri** e quindi fare clic su **Configura HTTP**.

4.  Nella finestra di dialogo **Configura criteri HTTP per la regola** deselezionare la casella di controllo **Verifica normalizzazione** e fare clic su **OK**.

5.  Nella finestra di dialogo **Proprietà** fare clic su **OK**.

6.  In Forefront TMG fare clic su **Applica** per abilitare le modifiche. Quando viene visualizzata la finestra di dialogo contenente la descrizione della**** modifica apportata alla configurazione, fare clic su **Applica**.

Dopo aver completato l'installazione, è possibile testare il server Office Web Apps utilizzando le procedure descritte nell'argomento [convalidare la configurazione del server Office Web Apps in Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

