---
title: 'Lync Server 2013: creare un criterio vocale e configurare i record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80537aabe132f1b83714d42244409224ca53f72d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Seguire questa procedura se si vuole creare un nuovo criterio vocale. Se si vuole modificare un criterio vocale, vedere [modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) per la procedura.

<div>


> [!NOTE]  
> Ogni criterio vocale deve avere almeno un record di utilizzo PSTN (Public Switched Telephone Network) associato. Per visualizzare un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale e visualizzare le relative proprietà, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-voice-policy"></a>Per creare un criterio vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **criteri vocali**.

4.  Nella pagina **criteri vocali** fare clic su **nuovo** e quindi selezionare un ambito per il nuovo criterio:
    
      - I **criteri del sito** si applicano a un intero sito, eccetto gli utenti o i gruppi assegnati a un criterio utente. Se si seleziona sito per un ambito di criteri, scegliere il sito nella finestra di dialogo **Seleziona sito** . Se è già stato creato un criterio vocale per un sito, il sito non viene visualizzato nella finestra di dialogo **Seleziona sito** .
    
      - I **criteri utente** possono essere applicati agli utenti o ai gruppi specificati.

5.  Se l'ambito dei criteri vocali è un utente, immettere un nome descrittivo per i criteri nel campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Se l'ambito dei criteri vocali è sito, il campo <STRONG>nome</STRONG> nei <STRONG>nuovi criteri vocali</STRONG> viene precompilato con il nome del sito e non può essere modificato.

    
    </div>

6.  Opzionale Immettere altre informazioni descrittive per il criterio vocale.

7.  Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ogni **funzionalità di chiamata** per il criterio vocale:
    
      - La funzionalità **escape** per la segreteria telefonica impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata.
        
        <div>
        

        > [!NOTE]  
        > Questa caratteristica può essere configurata solo tramite Lync Server Management Shell

        
        </div>
    
      - L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client. Lync Server 2013 offre una gamma molto più ampia di opzioni di configurazione per l'inoltro di chiamata. Ad esempio, se un'organizzazione non vuole consentire la trasmissione esterna delle chiamate in arrivo alla rete PSTN, un amministratore può applicare un criterio vocale speciale per distribuire questa restrizione. Abilitato per impostazione predefinita.
    
      - La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto. In Lync Server 2013, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al suo manager di chiamare tutte le destinazioni di chiamata simultanee del delegato. In questo modo il delegato offre maggiore flessibilità per rispondere alle chiamate indirizzate al responsabile. Abilitato per impostazione predefinita.
    
      - Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti. Abilitato per impostazione predefinita.
    
      - **Call Park** consente agli utenti di parcheggiare le chiamate in attesa e quindi prendere la chiamata da un altro telefono o client. Disabilitata per impostazione predefinita.
    
      - La **chiamata simultanea** consente alle chiamate in arrivo di squillare su altri telefoni (ad esempio, un cellulare) o altri dispositivi endpoint. Lync Server 2013 offre una gamma molto più ampia di opzioni di configurazione per la chiamata simultanea. Abilitato per impostazione predefinita.
    
      - La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team. Abilitato per impostazione predefinita.
    
      - La **reinstradazione PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti aziendali di essere reinstradati nella rete PSTN (Public Switched Telephone Network) se la WAN è congestionata o non disponibile. Abilitato per impostazione predefinita.
    
      - **L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo ammissione chiamata per un determinato utente. Disabilitata per impostazione predefinita.
        
        <div>
        

        > [!NOTE]  
        > Il criterio verrà ignorato solo per le chiamate in arrivo all'utente e non per le chiamate in uscita poste dall'utente. Una volta stabilita la sessione, il consumo di larghezza di banda verrà accuratamente registrato. Questa impostazione deve essere usata con parsimonia e deve essere riservata alle decisioni appropriate per il controllo dell'ammissione alle chiamate.

        
        </div>
    
      - La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite, ad esempio minacce bomba, usando l'interfaccia utente del client, che a sua volta contrassegna le chiamate nei record dettagli chiamata (CDRs). Disabilitata per impostazione predefinita.

8.  Per associare e configurare i record di utilizzo PSTN per questo criterio vocale, eseguire una delle operazioni seguenti:
    
      - Per scegliere uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare a questo criterio vocale e quindi fare clic su **OK**.
    
      - Per rimuovere un record di utilizzo PSTN da questo criterio vocale, evidenziare il record e fare clic su **Rimuovi**.
    
      - Per definire un nuovo record di utilizzo PSTN e associarlo a questo criterio vocale, eseguire le operazioni seguenti:
        
        1.  Fare clic su **nuovo**.
        
        2.  Nel campo **nome** immettere un nome descrittivo univoco per il record. Ad esempio, potresti voler creare un record di utilizzo PSTN denominato **Redmond** per i dipendenti a tempo pieno che si trovano a Redmond e un altro denominato **RedmondTemps** per i dipendenti temporanei.
            
            <div>
            

            > [!NOTE]  
            > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.

            
            </div>
        
        3.  Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:
            
              - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.
            
              - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Fare clic su **OK**.
    
      - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:
        
        1.  Evidenziare il record di utilizzo PSTN che si vuole modificare e quindi fare clic su **Mostra dettagli**.
        
        2.  Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:
            
              - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.
            
              - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e Lick **Show Details**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Fare clic su **OK**.

9.  Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.
    
    <div>
    

    > [!IMPORTANT]  
    > L'ordine in cui i record di utilizzo PSTN sono elencati nel criterio vocale è significativo. Lync Server attraversa l'elenco dall'alto verso il basso. Ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

10. Per associare e configurare i record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:
    
      - Per usare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo come criterio vocale, selezionare la route di opzione **usando gli utilizzi PSTN chiamata** dal menu a discesa.
    
      - Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Lync, selezionare l'opzione **Route per gli utenti di Lync interni solo** dal menu a discesa. Le chiamate non verranno inoltrate ai numeri PSTN esterni.
    
      - Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di quello usato per questo criterio vocale, selezionare la route di opzione **usando gli usi PSTN personalizzati** dal menu a discesa. Questa opzione Visualizza un controllo per selezionare i record di utilizzo PSTN esistenti o creare nuovi record di utilizzo PSTN in modo specifico per l'inoltro di chiamata e lo squillo simultaneo.
        
          - Per scegliere uno o più record da un elenco di record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri di inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.
        
          - Per rimuovere un record di utilizzo PSTN da questo inoltro di chiamata e dal criterio di squillo simultaneo, evidenziare il record e fare clic su **Rimuovi**.
        
          - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri di inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:
            
            1.  Fare clic su **nuovo**.
            
            2.  Nel campo **nome** immettere un nome descrittivo univoco per il record.
                
                <div>
                

                > [!NOTE]  
                > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.

                
                </div>
            
            3.  Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:
                
                  - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.
                
                  - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.
                
                  - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Fare clic su **OK**.
        
          - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:
            
            1.  Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.
            
            2.  Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:
                
                  - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.
                
                  - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.
                
                  - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Fare clic su **OK**.

11. Opzionale Immettere un numero per testare il criterio vocale e fare clic su **Vai**. I risultati del test vengono visualizzati in **numero tradotto per il test**.
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare un criterio vocale che non supera ancora il test e quindi riconfigurarlo in un secondo momento. Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.

    
    </div>

12. Fare clic su **OK**.

13. Nella pagina **criteri vocali** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

14. Opzionale La funzionalità di escape della segreteria telefonica rileva che una chiamata è stata immediatamente risolta dalla segreteria telefonica dell'utente e disconnette la chiamata alla segreteria telefonica per dispositivi mobili. In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente dando all'utente la possibilità di rispondere alla chiamata. Per informazioni dettagliate su come configurare un criterio per la segreteria telefonica, vedere [configurazione della modalità di escape della segreteria telefonica in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Visualizzare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configurazione della posta in uscita della segreteria telefonica in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

