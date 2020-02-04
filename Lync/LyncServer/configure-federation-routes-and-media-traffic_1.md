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
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728176"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

 


Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete. Dopo la migrazione al pool di piloti di Lync Server 2013, è necessario passare dalla Route federativo di Microsoft Office Communications Server 2007 R2 Edge Server alla route federativo di Lync Server 2013 Edge Servers.

Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Office Communications Server 2007 R2 Edge Server e Director a Lync Server 2013 Edge Server per una distribuzione a sito singolo.


> [!IMPORTANT]  
> Per modificare la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività della manutenzione per Lync Server 2013 e Office Communications Server 2007 R2 Edge Servers. L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione. È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima. Dovresti anche dare una notifica sufficiente agli utenti finali. Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione.




> [!IMPORTANT]  
> Se l'legacy Office Communications Server 2007 R2 Edge Server è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge Services e il servizio A/V Edge, le procedure descritte in questa sezione per la transizione dell'impostazione della Federazione a un server perimetrale di Lync Server 2013 non sono supportate. Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti da Office Communications Server 2007 R2 a Lync Server 2013, quindi rimuovere la Commissione da Office Communications Server 2007 R2 Edge Server prima di abilitare la Federazione Server Edge di Lync Server 2013. Per informazioni dettagliate, vedere gli argomenti seguenti: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Spostare gli utenti rimanenti in Lync Server 2013</A></P>
> <LI>
> <P>"Rimuovere server e ruoli server" in<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Se la Federazione XMPP viene instradata tramite un server perimetrale di Lync Server 2013, gli utenti legacy di Office Communications Server 2007 R2 non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, in criteri XMPP e i certificati sono stati configurati, il partner federato XMPP è stato configurato in Lync Server 2013 e infine le voci DNS sono state aggiornate.



Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile delegare i diritti utente appropriati e le autorizzazioni per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition. Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Per rimuovere l'associazione federativa Legacy dai siti di Lync Server 2013

1.  Aprire la topologia del pool di Pilot usando generatore di topologia.

2.  Nel riquadro sinistro passare al nodo del sito.

3.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.

4.  Selezionare **Route federativo** nel riquadro sinistro.

5.  In assegnazione della route federativo di sito deselezionare la casella di controllo accanto a **Consenti federazione SIP** per disabilitare la route federativo tramite **BackCompatSite**.
    
    ![Finestra di dialogo Modifica proprietà - Route di federazione](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Route di federazione")

6.  Fare clic su **OK** per chiudere la pagina Modifica proprietà.

7.  In **Generatore di topologie**selezionare il primo nodo **Lync Server**.

8.  Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federativo

1.  Da **Generatore di topologie**, dal menu **azione** fare clic su **Unisci topologia di Office Communications Server 2007 R2**.

2.  Fare clic su **Avanti** per continuare.

3.  Nella **configurazione specifica bordo**selezionare il nome di **dominio completo interno del server perimetrale** attualmente configurato per la Federazione e quindi fare clic su **Cambia**.
    
    ![Unisci topologia 2007 R2 - Specificare installazione server perimetrale](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Unisci topologia 2007 R2 - Specificare installazione server perimetrale")

4.  Fare clic su **Avanti** e accettare le impostazioni predefinite fino a raggiungere la pagina **specifica bordi esterni** :
    
    ![Pagina Specificare il perimetro esterno in Generatore di topologie](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Pagina Specificare il perimetro esterno in Generatore di topologie")

5.  In **specifica bordo esterno**deselezionare la casella **di controllo questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** . Verrà rimosso l'associazione di federazione con BackCompatSite.
    

    > [!IMPORTANT]  
    > Questo passaggio è importante. Devi deselezionare questa opzione per rimuovere l'associazione di federazione legacy.



6.  Fare clic su **Avanti** e accettare le impostazioni predefinite delle pagine rimanenti della procedura guidata.

7.  In **Riepilogo**, fare clic su **Avanti** per iniziare a unire le topologie.

8.  Nella colonna **stato** verificare che il valore sia **successo**e quindi fare clic su **fine** per chiudere la procedura guidata.

9.  Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.

10. Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.
    
    ![Generatore di topologie con sito visualizzato dopo l'unione](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Generatore di topologie con sito visualizzato dopo l'unione")
    
    Come illustrato nella figura precedente, la **federazione SIP** situata in **assegnazione Route federativo di sito** è impostata su **disabled**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Per configurare i certificati nel server perimetrale di Lync Server 2013

1.  Esportare il certificato proxy di accesso esterno, con la chiave privata, dal server perimetrale legacy di Office Communications Server 2007 R2.

2.  Nel server Edge di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.

3.  Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 dell'Edge Server.

4.  Il certificato di interfaccia interno del server Edge di Lync Server 2013 non deve essere modificato.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Per modificare la route Federation di Office Communications Server 2007 R2 per l'uso di Lync Server 2013 Edge Server

1.  Nel server Office Communications Server 2007 R2 Standard Edition o front end server aprire lo strumento di amministrazione di Office Communications Server 2007 R2.

2.  Nel riquadro sinistro espandere il nodo superiore e quindi fare clic con il pulsante destro del mouse sul nodo della **foresta** . Selezionare **Proprietà**e quindi fare clic su **proprietà globali**.

3.  Fare clic sulla scheda **Federazione** .

4.  Selezionare la casella di controllo per abilitare la Federazione e la connettività per messaggistica istantanea pubblica.

5.  Immettere il nome di dominio completo di Lync Server 2013 Edge Server e quindi fare clic su **OK**.
    
    ![Proprietà globali di Office Communications Server - Scheda Federazione](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Proprietà globali di Office Communications Server - Scheda Federazione")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Per attivare Lync Server 2013 Edge Server Federation

1.  Nel riquadro sinistro di generatore di topologia passare al nodo **pool di bordi** di Lync Server 2013.

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.
    

    > [!NOTE]  
    > La Federazione può essere abilitata solo per un singolo pool di Edge. Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi.



3.  Nella pagina **generale** selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .
    
    ![Modifica proprietà, Generale - Abilitazione della federazione perimetrale](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modifica proprietà, Generale - Abilitazione della federazione perimetrale")

4.  Fare clic su **OK** per chiudere la pagina Modifica proprietà.

5.  Passare quindi al nodo del sito.

6.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.

7.  Nel riquadro sinistro fare clic su **Route federativo**.

8.  In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Lync Server 2013 elencato.

9.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .
    
    ![Modifica proprietà, Generale - Associa pool di server perimetrali](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifica proprietà, Generale - Associa pool di server perimetrali")
    
    Per le distribuzioni multisito, completare questa procedura in ogni sito.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Per configurare il percorso multimediale in uscita di Lync Server 2013 Edge Server

1.  Da **Generatore di topologie**, passare al pool di Lync Server 2013 sotto i **server front end Standard Edition** o i **pool Front end Enterprise Edition**.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

3.  Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** .

4.  Nella casella a discesa selezionare il server Edge di Lync Server 2013.
    
    ![Finestra di dialogo Modifica proprietà - Associa pool di server perimetrali](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Associa pool di server perimetrali")

5.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche alla configurazione di Edge Server

1.  In **Generatore di topologie**selezionare il primo nodo **Lync Server**.

2.  Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.

3.  Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.
    

    > [!NOTE]  
    > Potrebbe essere visualizzato il messaggio seguente:<BR><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Office Communications Server 2007 R2 o Lync Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.</STRONG><BR>Questo avviso è previsto e può essere ignorato in modo sicuro.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Per verificare la Federazione e l'accesso remoto per gli utenti esterni

1.  Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.

2.  Per verificare lo stato di Federazione e accesso remoto, nella riga di comando digitare quanto segue:
    
        Get-CsAccessEdgeConfiguration

3.  Per abilitare la Federazione e l'accesso remoto, digitare quanto segue dalla riga di comando:
    
        Set-CsAccessEdgeConfiguration
    
    Per altre informazioni su questi cmdlet, vedere gli argomenti seguenti: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) e [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  Attendere che la replica sia stata completata prima di portare i server Edge di Lync Server 2013 online e verificare la Federazione e l'accesso esterno.

## <a name="to-configure-lync-server-2013-edge-server"></a>Per configurare Lync Server 2013 Edge Server

1.  Riunire tutti i server Edge di Lync Server 2013 online.

2.  Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) nel server perimetrale di Lync Server 2013, invece che nel server perimetrale legacy.
    

    > [!NOTE]  
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolvere il nuovo server di Access Edge di Lync Server. Per eseguire questa operazione con un'interruzione minima, ridurre il valore TTL per l'FQDN di Access Edge di Lync Server esterno, in modo che quando il DNS viene aggiornato per posizionare il puntatore sul nuovo server di Access Edge di Lync Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente.



3.  Arrestare quindi il **bordo di accesso di Lync Server** da ogni computer Edge Server.

4.  Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.

5.  Nell'elenco servizi individuare **Edge Access di Office Communications Server**.

6.  Fare clic con il pulsante destro del mouse sul nome dei servizi e quindi scegliere **Interrompi** per arrestare il servizio.

7.  Impostare il tipo di avvio su **disabled**.

8.  Fare clic su **OK** per chiudere la finestra **Proprietà** .

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Per testare la connettività degli utenti esterni e dell'accesso esterno

  - Utenti di almeno un dominio federato, un utente interno in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Test di messaggistica istantanea (IM), presenza, audio/video (A/V) e condivisione desktop.

  - Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning) che comunica con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2.

  - Verificare che gli utenti anonimi siano in grado di partecipare a conferenze.

  - Un utente ospitato in Office Communications Server 2007 R2 che usa l'accesso degli utenti remoti (accedendo a Office Communications Server 2007 R2 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.

  - Un utente ospitato in Lync Server 2013 che usa l'accesso degli utenti remoti (accedendo a Lync Server 2013 dall'esterno della Intranet ma senza VPN) con un utente in Lync Server 2013 e un utente in Office Communications Server 2007 R2. Test di messaggistica istantanea, presenza, A/V e condivisione desktop.

