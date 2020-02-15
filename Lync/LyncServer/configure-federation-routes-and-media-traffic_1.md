---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f4818e74bbc0f59900ebf7d8f0a2b79fcd003f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006662"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

 


La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota di Lync Server 2013, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali di Microsoft Office Communications Server 2007 R2 alla route di Federazione dei server perimetrali di Lync Server 2013.

Utilizzare le procedure seguenti per la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director di Office Communications Server 2007 R2 al server perimetrale di Lync Server 2013, per una distribuzione a sito singolo.


> [!IMPORTANT]  
> La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server perimetrali di Lync Server 2013 e Office Communications Server 2007 R2. Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi. È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti. È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo. Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate.




> [!IMPORTANT]  
> Se il server perimetrale Office Communications Server 2007 R2 legacy è configurato in modo da utilizzare lo stesso FQDN per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione per la transizione dell'impostazione di federazione a un server perimetrale di Lync Server 2013 non sono supportate. Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti da Office Communications Server 2007 R2 a Lync Server 2013, quindi rimuovere il server perimetrale di Office Communications Server 2007 R2 prima di abilitare la Federazione Server perimetrale di Lync Server 2013. Per informazioni dettagliate, vedere i seguenti argomenti: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Spostare gli utenti rimanenti in Lync Server 2013</A></P>
> <LI>
> <P>"Rimozione di server e ruoli del server" all'indirizzo<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Se la Federazione XMPP viene instradata attraverso un server perimetrale di Lync Server 2013, gli utenti di Office Communications Server 2007 R2 legacy non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, i criteri XMPP e i certificati sono stati configurati, il partner federato XMPP è stato configurato su Lync Server 2013 e infine le voci DNS sono state aggiornate.



Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario aver eseguito l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È inoltre possibile delegare le autorizzazioni e i diritti utente appropriati per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition. Per poter apportare altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Per rimuovere l'associazione di federazione legacy dai siti di Lync Server 2013

1.  Aprire la topologia pool pilota utilizzando Generatore di topologie.

2.  Nel riquadro sinistro passare al nodo del sito.

3.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà **.

4.  Selezionare **Route di federazione** nel riquadro sinistro.

5.  In Assegnazione route federazione sito deselezionare la casella di controllo accanto a **Abilita federazione SIP** per disabilitare la route di federazione tramite **BackCompatSite**.
    
    ![Finestra di dialogo Modifica proprietà, route di Federazione](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Finestra di dialogo Modifica proprietà, route di Federazione")

6.  Fare clic su  **OK** per chiudere la pagina Modifica proprietà.

7.  In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.

8.  Nel menu **Azione** fare clic su **Pubblica topologia** e quindi completare la procedura guidata.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federato

1.  In **Generatore di tipologie** scegliere **Unisci la topologia Office Communications Server 2007 R2** dal menu **Azione**.

2.  Fare clic su **Avanti** per continuare.

3.  In **Specificare installazione server perimetrale** selezionare il nome **FQDN interno del server perimetrale** attualmente configurato per la federazione e quindi fare clic su **Cambia**.
    
    ![Unire la topologia OCS 2007 R2, specificare l'installazione del server perimetrale](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Unire la topologia OCS 2007 R2, specificare l'installazione del server perimetrale")

4.  Fare clic su **Avanti** e accettare le impostazioni predefinite finché non viene visualizzata la pagina **Specificare il perimetro esterno**:
    
    ![Generatore di topologie specificare la pagina perimetro esterno](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Generatore di topologie specificare la pagina perimetro esterno")

5.  In **Specificare il perimetro esterno** deselezionare la casella di controllo **Questo pool di server perimetrali è utilizzato per la federazione e la connettività di messaggistica istantanea pubblica**. In questo modo verrà rimossa l'associazione di federazione con BackCompatSite.
    

    > [!IMPORTANT]  
    > Questo passaggio è importante. È necessario deselezionare questa opzione per rimuovere l'associazione di federazione legacy.



6.  Fare clic su **Avanti** e accettare le impostazioni predefinite delle pagine rimanenti della procedura guidata.

7.  In **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie.

8.  Nella colonna **stato** verificare che il valore sia **esito positivo**e quindi fare clic su **fine** per chiudere la procedura guidata.

9.  Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.

10. Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata.
    
    ![Generatore di topologie con sito visualizzato dopo l'Unione](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generatore di topologie con sito visualizzato dopo l'Unione")
    
    Come illustrato nella figura precedente, la **federazione SIP** presente in **Assegnazione route federazione sito** è impostata su **Disabilitata**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Per configurare i certificati nel server perimetrale Lync Server 2013

1.  Esportare il certificato del proxy di accesso esterno, con la chiave privata, dal server perimetrale Office Communications Server 2007 R2 legacy.

2.  Nel server perimetrale di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.

3.  Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 del server perimetrale.

4.  Il certificato dell'interfaccia interna del server perimetrale di Lync Server 2013 non deve essere modificato.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Per modificare la route di federazione di Office Communications Server 2007 R2 per l'utilizzo del server perimetrale Lync Server 2013

1.  Nel server Office Communications Server 2007 R2 Standard Edition o front end server aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Nel riquadro sinistro espandere il nodo superiore e quindi fare clic con il pulsante destro del mouse sul nodo **Foresta**. Scegliere **Proprietà** e quindi fare clic su **Proprietà globali**.

3.  Fare clic sulla scheda **Federazione**.

4.  Selezionare la casella di controllo per abilitare la federazione e la connettività per messaggistica istantanea pubblica.

5.  Immettere il nome di dominio completo del server perimetrale di Lync Server 2013 e quindi fare clic su **OK**.
    
    ![Proprietà globali di OCS, scheda Federazione](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Proprietà globali di OCS, scheda Federazione")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Per abilitare la federazione del server perimetrale di Lync Server 2013

1.  In Generatore di topologie, nel riquadro sinistro, passare al nodo Pool di server **perimetrali** di Lync 2013.

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà **.
    

    > [!NOTE]  
    > La Federazione può essere abilitata solo per un singolo pool di server perimetrali. In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati.



3.  Nella pagina **Generale** selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)**.
    
    ![Modifica proprietà, generale, Abilita federazione Edge](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modifica proprietà, generale, Abilita federazione Edge")

4.  Fare clic su  **OK** per chiudere la pagina Modifica proprietà.

5.  Passare quindi al nodo del sito.

6.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà **.

7.  Nel riquadro sinistro fare clic su  **Route di federazione **.

8.  In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server perimetrale di Lync Server 2013 elencato.

9.  Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **.
    
    ![Modifica proprietà, generale, associa pool di server perimetrali](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifica proprietà, generale, associa pool di server perimetrali")
    
    Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Per configurare il percorso del contenuto multimediale in uscita dei server perimetrali Lync Server 2013

1.  In **Generatore di topologie**passare al pool di Lync Server 2013 al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà **.

3.  Nella sezione  **Associazioni ** selezionare la casella di controllo  **Associa pool di server perimetrali (per componenti multimediali) **.

4.  Nella casella a discesa selezionare il server perimetrale di Lync Server 2013.
    
    ![Finestra di dialogo Modifica proprietà, associa pool di server perimetrali](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Finestra di dialogo Modifica proprietà, associa pool di server perimetrali")

5.  Fare clic su **OK** per chiudere la pagina **Modifica proprietà**.

## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche di configurazione del server perimetrale

1.  In **Generatore di topologie** selezionare il nodo principale **Lync Server**.

2.  Scegliere **Pubblica topologia** dal menu **Azione** e quindi completare la procedura guidata.

3.  Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.
    

    > [!NOTE]  
    > Potrebbe essere visualizzato il messaggio seguente:<BR><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questa situazione può verificarsi durante la migrazione a una versione successiva del prodotto. In questo caso, per la federazione viene utilizzato attivamente un solo server perimetrale. Verificare che il record SRV DNS punti al server perimetrale corretto. Se si desidera distribuire più server perimetrali federati in modo che siano attivi contemporaneamente (ovvero non in uno scenario di migrazione), verificare che tutti i partner federati utilizzino Office Communications Server 2007 R2 o versione successiva e che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la federazione.</STRONG><BR>Si tratta di un avviso previsto che può essere tranquillamente ignorato.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Per verificare la federazione e l'accesso remoto per gli utenti esterni

1.  Dal front end server Lync Server 2013 aprire Lync Server Management Shell.

2.  Per verificare lo stato della federazione e dell'accesso remoto, digitare dalla riga di comando quanto segue:
    
        Get-CsAccessEdgeConfiguration

3.  Per abilitare la federazione e l'accesso remoto, digitare dalla riga di comando quanto segue:
    
        Set-CsAccessEdgeConfiguration
    
    Per ulteriori informazioni su questi cmdlet, vedere i seguenti argomenti: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) e [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).

4.  Attendere che la replica sia stata completata prima di portare i server perimetrali di Lync Server 2013 online e verificare la Federazione e l'accesso esterno.

## <a name="to-configure-lync-server-2013-edge-server"></a>Per configurare il server perimetrale Lync Server 2013

1.  Portare online tutti i server perimetrali di Lync Server 2013.

2.  Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Lync Server 2013, anziché al server perimetrale legacy.
    

    > [!NOTE]  
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS A per la federazione in modo che rimandi al nuovo server Lync Server Access Edge. Per eseguire questa operazione con il minimo impatto sul servizio, ridurre il valore TTL dell'FQDN del Lync Server Access Edge esterno in modo che quando il DNS viene aggiornato per puntare al nuovo server Lync Server Access Edge, la federazione e l'accesso remoto vengono aggiornati rapidamente.



3.  Successivamente, arrestare **Lync Server Access Edge** da ogni computer server perimetrale.

4.  Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.

5.  Individuare **Office Communications Server Access Edge** tra i servizi elencati.

6.  Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestare il servizio.

7.  Impostare il tipo di avvio su **Disabilitato**.

8.  Fare clic su **OK** per chiudere la finestra **Proprietà**.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Per testare la connettività degli utenti esterni e dell'accesso esterno

  - Utenti provenienti da almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Testare la messaggistica istantanea, il traffico audio/video e la condivisione del desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea supportato dall'organizzazione (e per i quali è stato completato il provisioning) che comunicano con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.

  - Verificare che gli utenti anonimi siano in grado di partecipare alle conferenze.

  - Un utente ospitato in Office Communications Server 2007 R2 utilizzando l'accesso utente remoto (connessione a Office Communications Server 2007 R2 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.

  - Un utente ospitato in Lync Server 2013 utilizzando l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della rete Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Testare la messaggistica istantanea, la presenza, il traffico audio/video e la condivisione del desktop.

