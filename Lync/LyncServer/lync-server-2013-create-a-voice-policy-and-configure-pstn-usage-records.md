---
title: 'Lync Server 2013: creare un criterio vocale e configurare i record di utilizzo PSTN'
description: 'Lync Server 2013: creare un criterio vocale e configurare i record di utilizzo PSTN.'
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
ms.openlocfilehash: 55833572b5ca79019d5037406ae530ef5591b6fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562452"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se si desidera creare un nuovo criterio vocale, attenersi alla seguente procedura. Se si desidera modificare un criterio vocale, vedere [modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) per la procedura.

<div>


> [!NOTE]  
> Ogni criterio vocale deve disporre di almeno un record di utilizzo PSTN (Public Switched Telephone Network) associato. Per visualizzare un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione di VoIP aziendale e visualizzarne le proprietà, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-voice-policy"></a>Per creare un criterio vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **criteri vocali**.

4.  Nella pagina **criteri vocali** fare clic su **nuovo** e quindi selezionare un ambito per il nuovo criterio:
    
      - I **criteri del sito** si applicano a un intero sito, ad eccezione degli utenti o dei gruppi assegnati a un criterio utente. Se si seleziona sito per un ambito di criteri, scegliere il sito nella finestra di dialogo **Seleziona un sito** . Se per un sito è già stato creato un criterio vocale, il sito non viene visualizzato nella finestra di dialogo **Seleziona un sito** .
    
      - I **criteri utente** possono essere applicati a utenti o gruppi specificati.

5.  Se l'ambito dei criteri vocali è utente, immettere un nome descrittivo per il criterio nel campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Se l'ambito del criterio vocale è sito, il campo <STRONG>nome</STRONG> nei <STRONG>nuovi criteri vocali</STRONG> viene prepopolato con il nome del sito e non può essere modificato.

    
    </div>

6.  Optional Immettere ulteriori informazioni descrittive per il criterio vocale.

7.  Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ognuna delle **funzionalità di chiamata** per i criteri vocali:
    
      - La **funzione di escape della segreteria telefonica** fa in modo che le chiamate non vengano immediatamente instradate al sistema di segreteria telefonica del dispositivo mobile dell'utente quando è attivo lo squillo simultaneo, e il telefono è spento, scarico o fuori copertura di rete.
        
        <div>
        

        > [!NOTE]  
        > Questa funzionalità può essere configurata solo tramite Lync Server Management Shell

        
        </div>
    
      - L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client. Lync Server 2013 offre un'ampia gamma di opzioni di configurazione per l'inoltro di chiamata. Ad esempio, se l'organizzazione desidera evitare che le chiamate in entrata vengano inoltrate esternamente a PSTN, l'amministratore può applicare un criterio vocale specifico per la distribuzione di questa limitazione. La funzionalità è abilitata per impostazione predefinita.
    
      - La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto. In Lync Server 2013, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al proprio manager di suonare tutti gli obiettivi di squillo simultanei del delegato. In questo modo, al delegato viene offerta una maggiore flessibilità quando si trova a dover rispondere a chiamate destinate al proprio manager. La funzionalità è abilitata per impostazione predefinita.
    
      - Il **trasferimento di chiamata** consente agli utenti di trasferire chiamate ad altri utenti. Funzionalità abilitata per impostazione predefinita.
    
      - **Parcheggio di chiamata** consente agli utenti di parcheggiare le chiamate in attesa e quindi di prendere la chiamata da un altro telefono o client. Questa opzione è disabilitata per impostazione predefinita.
    
      - **Squillo simultaneo** consente lo squillo in telefoni aggiuntivi, ad esempio un telefono cellulare, o in altri dispositivi endpoint per le chiamate in arrivo. Lync Server 2013 offre una vasta gamma di opzioni di configurazione per lo squillo simultaneo. Funzionalità abilitata per impostazione predefinita.
    
      - **Intercettazione team**: consente agli utenti di un team definito di rispondere alle chiamate per altri membri del team. Questa opzione è abilitata per impostazione predefinita.
    
      - **Abilita reindirizzamento PSTN**: consente il rendirizzamento di chiamate effettuate da utenti assegnati ai criteri ad altri utenti aziendali nella rete PSTN in caso di congestione o non disponibilità della rete WAN. Questa opzione è abilitata per impostazione predefinita.
    
      - L'**override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni per i criteri di controllo di ammissione di chiamata per un particolare utente. Funzionalità disabilitata per impostazione predefinita.
        
        <div>
        

        > [!NOTE]  
        > Verrà eseguito l'override dei criteri solo per le chiamate in arrivo all'utente e non per le chiamate in uscita effettuate dall'utente. Dopo che la sessione viene stabilita, l'utilizzo della larghezza di banda viene registrato accuratamente. Questa impostazione deve essere utilizzata con parsimonia e deve essere riservata alle decisioni appropriate per il controllo di ammissione di chiamata.

        
        </div>
    
      - L' **analisi chiamata** non consentita consente agli utenti di segnalare chiamate non consentite (ad esempio minacce di bomba) utilizzando l'interfaccia utente del client, che a sua scelta contrassegna le chiamate nei record dettagli chiamata (CDRs). Questa opzione è disabilitata per impostazione predefinita.

8.  Per associare e configurare record di utilizzo PSTN per i criteri vocali, eseguire una delle operazioni seguenti:
    
      - Per scegliere uno o più record da un elenco di record di utilizzo PSTN disponibile nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare al criterio vocale e quindi fare clic su **OK**.
    
      - Per rimuovere un record di utilizzo PSTN dal criterio vocale, evidenziarlo e quindi fare clic su **Rimuovi**.
    
      - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri vocali, eseguire le operazioni seguenti:
        
        1.  Fare clic su **Nuovo**.
        
        2.  Nel campo **Nome** immettere un nome descrittivo univoco per il record. Ad esempio, potrebbe essere necessario creare un record di utilizzo PSTN denominato **Redmond** per i dipendenti a tempo pieno situati a Redmond e un altro denominato **RedmondTemps** per i dipendenti temporanei.
            
            <div>
            

            > [!NOTE]  
            > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.

            
            </div>
        
        3.  Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:
            
              - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.
            
              - Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Fare clic su **OK**.
    
      - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:
        
        1.  Evidenziare il record di utilizzo PSTN che si desidera modificare e quindi fare clic su **Mostra dettagli**.
        
        2.  Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:
            
              - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.
            
              - Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e leccare **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Fare clic su **OK**.

9.  Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.
    
    <div>
    

    > [!IMPORTANT]  
    > L'ordine in cui i record di utilizzo PSTN sono elencati nei criteri vocali è significativo. Lync Server attraversa l'elenco dall'alto verso il basso. È consigliabile organizzare l'elenco in base a frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

10. Per associare e configurare record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:
    
      - Per utilizzare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa.
    
      - Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Lync, selezionare la **Route di opzione per gli utenti interni di Lync solo** dal menu a discesa. Le chiamate non verranno inoltrare ai numeri PSTN esterni.
    
      - Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli utilizzati per questo criterio vocale, selezionare la route delle opzioni **utilizzando gli utilizzi PSTN personalizzati** dal menu a discesa. Questa opzione consente di visualizzare un controllo per selezionare i record di utilizzo PSTN esistenti o creare nuovi record di utilizzo PSTN in modo specifico per l'inoltro di chiamata e lo squillo simultaneo.
        
          - Per scegliere uno o più record in un elenco dei record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri vocali dell'inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.
        
          - Per rimuovere un record di utilizzo PSTN dal criterio vocale dell'inoltro di chiamata e squillo simultaneo, evidenziarlo e quindi fare clic su **Rimuovi**.
        
          - Per definire un nuovo record di utilizzo PSTN e associarlo al criterio vocale dell'inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:
            
            1.  Fare clic su **Nuovo**.
            
            2.  Nel campo **Nome** immettere un nome descrittivo univoco per il record.
                
                <div>
                

                > [!NOTE]  
                > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.

                
                </div>
            
            3.  Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:
                
                  - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.
                
                  - Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.
                
                  - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Fare clic su **OK**.
        
          - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:
            
            1.  Evidenziare il record di utilizzo PSTN che si desidera modificare e fare clic su **Mostra dettagli**.
            
            2.  Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:
                
                  - Per scegliere una o più route da un elenco di tutte le route disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.
                
                  - Per rimuovere una route dal record di utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
                
                  - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Fare clic su **OK**.

11. (Facoltativo) Immettere un numero per testare il criteri vocale e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero convertito da testare**.
    
    <div>
    

    > [!NOTE]  
    > È possibile salvare i criteri locali che non hanno ancora superato il test e quindi riconfigurarli in seguito. Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.

    
    </div>

12. Fare clic su **OK**.

13. Nella pagina **Criteri vocali** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

14. (Facoltativo) La funzione di escape della segreteria telefonica rileva quando una chiamata viene risposta automaticamente dalla segreteria telefonica del dispositivo mobile dell'utente, e la disconnette dalla segreteria. In questo modo, la chiamata continua a squillare sugli altri endpoint dell'utente, consentendo a quest'ultimo di rispondere. Per informazioni dettagliate su come configurare un criterio di segreteria telefonica, vedere [Configuring Voice mail Escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Visualizzare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configurazione della funzionalità di escape della segreteria telefonica in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

