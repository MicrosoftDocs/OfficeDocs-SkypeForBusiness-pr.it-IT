---
title: Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Riepilogo: creare o modificare i criteri vocali e configurare i record di utilizzo PSTN utilizzando il Skype for Business Server di controllo.'
ms.openlocfilehash: 5dedb504a6d2d3e75b168bf32ff1f0ccb7ed94f8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828379"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business

**Riepilogo:** Creare o modificare i criteri vocali e configurare i record di utilizzo PSTN utilizzando il Skype for Business Server di controllo.

> [!NOTE]
> A ogni criterio vocale deve essere associato almeno un record di utilizzo PSTN (Public Switched Telephone Network). Per visualizzare un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione di VoIP aziendale e visualizzarne le proprietà, vedere [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Per creare un criterio vocale

1. Aprire Skype for Business Server Pannello di controllo.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Criteri vocali.**

3. Nella pagina **Criteri vocali** fare clic su **Nuovo** e quindi selezionare un ambito per il nuovo criterio:

   - **I criteri sito** si applicano a un intero sito, ad eccezione di tutti gli utenti o gruppi assegnati a un criterio utente. Se si seleziona Sito per un ambito di criteri, scegliere il sito nella **finestra di dialogo Seleziona** sito. Se è già stato creato un criterio vocale per un sito, il sito non verrà visualizzato nella **finestra di** dialogo Seleziona un sito.

   - **I criteri utente** possono essere applicati a utenti o gruppi specifici.

4. Se l'ambito dei criteri vocali è Utente, immettere un nome descrittivo per il criterio nel **campo** Nome.

    > [!NOTE]
    > Se l'ambito dei criteri vocali è Site, il campo **Name** in **New Voice Policy** viene prepopolato con il nome del sito e non può essere modificato.

5. (Facoltativo) Immettere ulteriori informazioni descrittive per il criterio vocale.

6. Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ognuna delle funzionalità **di chiamata** per questo criterio vocale:

   - **L'escape** della casella vocale impedisce che le chiamate vengano instradati immediatamente al sistema di caselle vocali del telefono cellulare dell'utente quando è configurato lo squillo simultaneo e il telefono è spento, fuori batteria o fuori intervallo.

     > [!NOTE]
     > Questa funzionalità è configurabile solo tramite Skype for Business Server Management Shell

   - L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client. Skype for Business Server offre una gamma notevolmente più ampia di opzioni di configurazione per l'inoltro di chiamata. Ad esempio, se l'organizzazione desidera evitare che le chiamate in entrata vengano inoltrate esternamente a PSTN, l'amministratore può applicare un criterio vocale specifico per la distribuzione di questa limitazione. La funzionalità è abilitata per impostazione predefinita.

   - La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto. In Skype for Business Server, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al proprio manager di squillare tutte le destinazioni di squillo simultaneo del delegato. In questo modo, al delegato viene offerta una maggiore flessibilità quando si trova a dover rispondere a chiamate destinate al proprio manager. La funzionalità è abilitata per impostazione predefinita.

   - Il **trasferimento di chiamata** consente agli utenti di trasferire chiamate ad altri utenti. Funzionalità abilitata per impostazione predefinita.

   - **Il parcheggio di** chiamata consente agli utenti di parcheggiare le chiamate in attesa e quindi di prelevare la chiamata da un altro telefono o client. Questa opzione è disabilitata per impostazione predefinita.

   - **Squillo simultaneo** consente lo squillo in telefoni aggiuntivi, ad esempio un telefono cellulare, o in altri dispositivi endpoint per le chiamate in arrivo. Skype for Business Server offre una gamma significativamente più ampia di opzioni di configurazione per lo squillo simultaneo. Funzionalità abilitata per impostazione predefinita.

   - L'**intercettazione team** consente agli utenti in uno team specificato di rispondere alle chiamate per gli altri membri del team. Funzionalità abilitata per impostazione predefinita.

   - **Il reindirizzamento PSTN** consente di reinstradare le chiamate effettuate da utenti assegnati a questo criterio ad altri utenti aziendali sulla rete PSTN se la rete WAN è congestionata o non disponibile. Funzionalità abilitata per impostazione predefinita.

   - L'**override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni per i criteri di controllo di ammissione di chiamata per un particolare utente. Funzionalità disabilitata per impostazione predefinita.

     > [!NOTE]
     > Verrà eseguito l'override dei criteri solo per le chiamate in arrivo all'utente e non per le chiamate in uscita effettuate dall'utente. Dopo che la sessione viene stabilita, l'utilizzo della larghezza di banda viene registrato accuratamente. Questa impostazione deve essere utilizzata con parsimonio e deve essere riservata per le decisioni appropriate relative al controllo di ammissione di chiamata.

   - **L'analisi delle chiamate** dannose consente agli utenti di segnalare chiamate dannose (ad esempio minacce) tramite l'interfaccia utente del client, che a sua volta contrassegna le chiamate nei record dettagli chiamata (CDR). Questa funzionalità è disabilitata per impostazione predefinita.

   - **Opzioni occupato** consente di abilitare o disabilitare le opzioni occupato per il criterio vocale specificato. Opzioni occupato consente di instradare le chiamate in arrivo alla segreteria telefonica o rifiutate con un segnale di occupato quando l'utente di destinazione della chiamata è sul telefono. Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016. Se si controlla questo parametro, vengono abilitate le opzioni occupato e se si deseleziona questa opzione vengono disabilitate le opzioni occupato. Per ulteriori informazioni, vedere [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) e Install and configure Busy Options for [Skype for Business Server](install-and-configure-busy-options.md).

7. Per associare e configurare record di utilizzo PSTN per i criteri vocali, eseguire una delle operazioni seguenti:

   - Per scegliere uno o più record da un elenco di record di utilizzo PSTN disponibile nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare al criterio vocale e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN dal criterio vocale, evidenziarlo e quindi fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri vocali, eseguire le operazioni seguenti:

     a. Fare clic su **Nuova regola**.

     b. Nel campo **Nome** immettere un nome descrittivo univoco per il record. Ad esempio, è possibile creare un record di utilizzo PSTN denominatoRedmond per i dipendenti a tempo pieno che si trovano a Redmond e un altro denominatoRedmondTemps per i dipendenti temporanei.

     > [!NOTE]
     > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato.

     c. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, evidenzia la route e quindi fai clic su **Rimuovi.**

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     d. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:

     a. Evidenziare il record di utilizzo PSTN che si desidera modificare e quindi fare clic **su Mostra dettagli**.

     b. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route da questo record di utilizzo PSTN, evidenzia la route e quindi fai clic su **Rimuovi.**

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e **leccare Mostra dettagli**.

     c. Fare clic su **OK**.

8. Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia su o giù.

    > [!IMPORTANT]
    > L'ordine in cui i record di utilizzo PSTN sono elencati nei criteri vocali è significativo. Skype for Business Server l'elenco dall'alto verso il basso. È consigliabile organizzare l'elenco in base a frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Per associare e configurare record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per utilizzare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa.

   - Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti Skype for Business interni, selezionare l'opzione Instrada solo agli utenti Skype for Business interni dal menu **a** discesa. Le chiamate non verranno inoltrare ai numeri PSTN esterni.

   - Per specificare record di utilizzo PSTN diversi per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli utilizzati per questo criterio vocale, selezionare l'opzione **Route using custom PSTN usages** from the drop-down menu. Questa opzione consente di visualizzare un controllo per selezionare i record di utilizzo PSTN esistenti o per creare nuovi record di utilizzo PSTN specifici per l'inoltro di chiamata e lo squillo simultaneo.

   - Per scegliere uno o più record in un elenco dei record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri vocali dell'inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN dal criterio vocale dell'inoltro di chiamata e squillo simultaneo, evidenziarlo e quindi fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo al criterio vocale dell'inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:

     a. Fare clic su **Nuova regola**.

     b. Nel campo **Nome** immettere un nome descrittivo univoco per il record.

     > [!NOTE]
     > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato.

     c. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     d. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:

     a. Evidenziare il record di utilizzo PSTN che si desidera modificare e fare clic **su Mostra dettagli.**

     b. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route da un elenco di tutte le route disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

10. (Facoltativo) Immettere un numero per testare il criteri vocale e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero convertito da testare**.

11. Fare clic su **OK**.

12. Nella pagina **Criteri vocali** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il **comando Commit all** per pubblicare la modifica della configurazione. Per informazioni dettagliate, [vedere Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

13. (Facoltativo) L'escape della segreteria telefonica rileva che la segreteria telefonica dell'utente ha immediatamente risposto a una chiamata e disconnette la chiamata al sistema di caselle vocali del telefono cellulare. In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente, offrendo all'utente la possibilità di rispondere alla chiamata. Per informazioni dettagliate su come configurare un criterio di segreteria telefonica, vedere [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Per modificare criteri vocali

1. Aprire Skype for Business Server Pannello di controllo.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Criteri vocali**.

3. Nella pagina **Criteri vocali** fare doppio clic sui nomi dei criteri vocali.

    > [!NOTE]
    > L'ambito e il nome sono stati impostati durante la creazione dei criteri vocali e non possono essere modificati.

4. Facoltativo: in **Modifica criterio vocale** immettere informazioni descrittive aggiuntive per i criteri vocali.

5. Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ogni opzione presente in **Funzionalità di chiamata**:

   - **L'escape** della casella vocale impedisce che le chiamate vengano instradati immediatamente al sistema di caselle vocali del telefono cellulare dell'utente quando è configurato lo squillo simultaneo e il telefono è spento, fuori batteria o fuori intervallo.

     > [!NOTE]
     > Questa funzionalità è configurabile solo tramite Skype for Business Server Management Shell

   - L'**inoltro di chiamata** consente agli utenti di inoltrare chiamate ad altri telefoni e dispositivi client. Skype for Business Server offre una gamma notevolmente più ampia di opzioni di configurazione per l'inoltro di chiamata. Ad esempio, se l'organizzazione desidera evitare che le chiamate in entrata vengano inoltrate esternamente a PSTN, l'amministratore può applicare un criterio vocale specifico per la distribuzione di questa limitazione. La funzionalità è abilitata per impostazione predefinita.

   - La **delega** consente agli utenti di specificare altri utenti per l'invio e la ricezione delle chiamate per loro conto. In Skype for Business Server, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al proprio manager di squillare tutte le destinazioni di squillo simultaneo del delegato. In questo modo, al delegato viene offerta una maggiore flessibilità quando si trova a dover rispondere a chiamate destinate al proprio manager. La funzionalità è abilitata per impostazione predefinita.

   - **Trasferimento chiamata**: consente agli utenti di trasferire chiamate ad altri utenti. Questa opzione è abilitata per impostazione predefinita.

   - **Parcheggio di chiamata**: consente agli utenti di eseguire il parcheggio di chiamate in attesa e quindi di rispondere alla chiamata da un telefono o un client diverso. Questa opzione è disabilitata per impostazione predefinita.

   - **Squillo simultaneo** consente lo squillo in telefoni aggiuntivi, ad esempio un telefono cellulare, o in altri dispositivi endpoint per le chiamate in arrivo. Skype for Business Server offre una gamma significativamente più ampia di opzioni di configurazione per lo squillo simultaneo. Funzionalità abilitata per impostazione predefinita.

   - L'**intercettazione team** consente agli utenti in uno team specificato di rispondere alle chiamate per gli altri membri del team. Funzionalità abilitata per impostazione predefinita.

   - **Il reindirizzamento PSTN** consente di reinstradare le chiamate effettuate da utenti assegnati a questo criterio ad altri utenti aziendali sulla rete PSTN se la rete WAN è congestionata o non disponibile. Funzionalità abilitata per impostazione predefinita.

   - **L'override dei criteri di** larghezza di banda consente agli amministratori di ignorare le decisioni relative ai criteri di controllo di ammissione di chiamata per un determinato utente. Questa opzione è disabilitata per impostazione predefinita.

     > [!NOTE]
     > Verrà eseguito l'override dei criteri solo per le chiamate in arrivo all'utente e non per le chiamate in uscita effettuate dall'utente. Dopo che la sessione viene stabilita, l'utilizzo della larghezza di banda viene registrato accuratamente. Questa impostazione deve essere utilizzata con cautela.

   - **L'analisi delle chiamate** dannose consente agli utenti di segnalare chiamate dannose (ad esempio minacce) tramite l'interfaccia utente del client, che a sua volta contrassegna le chiamate nelle richieste cdR. Questa opzione è disabilitata per impostazione predefinita.

6. Per associare e configurare record di utilizzo PSTN per i criteri vocali, eseguire una delle operazioni seguenti:

   - Per scegliere uno o più record da un elenco di record di utilizzo PSTN disponibile nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare al criterio vocale e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN dal criterio vocale, evidenziarlo e quindi fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri vocali, eseguire le operazioni seguenti:

     a. Fare clic su **Nuova regola**.

     b. Nel campo **Nome** immettere un nome descrittivo univoco per il record. È ad esempio possibile creare un record di utilizzo PSTN denominatoRedmond per i dipendenti a tempo pieno che si trovano a Redmond e un altro record denominatoRedmondTemps per i dipendenti temporanei.

     > [!NOTE]
     > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato.

     c. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     d. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:

     a. Evidenziare il record di utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.

     b. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route da un elenco di tutte le route disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

7. Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia su o giù.

    > [!NOTE]
    > L'ordine in cui i record di utilizzo PSTN sono elencati nei criteri vocali è significativo. Skype for Business Server l'elenco dall'alto verso il basso. È consigliabile organizzare l'elenco in base a frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Per associare e configurare record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per utilizzare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa.

   - Per consentire l'inoltro di chiamata e lo squillo  simultaneo solo agli utenti Skype for Business interni, selezionare Instrada solo agli utenti Skype for Business interni dal menu a discesa. Le chiamate non verranno inoltrare ai numeri PSTN esterni.

   - Per specificare record di utilizzo PSTN differenti per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli usati per questo criterio vocale, selezionare l'opzione **Route tramite gli usi PSTN di chiamata** dal  menu a discesa. Questa opzione visualizza un controllo che consente di selezionare i record di utilizzo PSTN esistenti, o di crearne di nuovi, specifici per l'inoltro di chiamata e lo squillo simultaneo.

   - Per scegliere uno o più record in un elenco dei record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri vocali dell'inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN dal criterio vocale dell'inoltro di chiamata e squillo simultaneo, evidenziarlo e quindi fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo al criterio vocale dell'inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:

     a. Fare clic su **Nuova regola**.

     b. Nel campo **Nome** immettere un nome descrittivo univoco per il record.

     > [!NOTE]
     > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato.

     c. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

   - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record di utilizzo PSTN, evidenziarla e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata al record di utilizzo PSTN, evidenziarla e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     d. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato al criterio vocale, eseguire le operazioni seguenti:

     a. Evidenziare il record di utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.

     b. Utilizzare uno dei metodi seguenti per associare e configurare route per il record di utilizzo PSTN:

     - Per scegliere una o più route nell'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**, evidenziare le route che si desidera associare al record di utilizzo PSTN e quindi fare clic su **OK**.

     - Per rimuovere una route dal record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Per modificare una route già associata al record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     c. Fare clic su **OK**.

9. (Facoltativo) Immettere un numero per testare il criteri vocale e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero convertito da testare**.

10. Fare clic su **OK**.

11. Nella pagina **Criteri vocali** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Quando si creano o modificano criteri vocali, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica di configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

12. (Facoltativo) L'escape della segreteria telefonica rileva che la segreteria telefonica dell'utente ha immediatamente risposto a una chiamata e disconnette la chiamata al sistema di caselle vocali del telefono cellulare. In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente, offrendo all'utente la possibilità di rispondere alla chiamata. Per informazioni dettagliate su come configurare un criterio di segreteria telefonica, vedere [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).

## <a name="see-also"></a>Vedere anche

[Visualizzare i record di utilizzo PSTN in Skype for Business](view-pstn-usage-records.md)

[Creare o modificare una route vocale in Skype for Business](create-or-modify-a-voice-route.md)

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business](voice-route-config-changes.md)

[Configurare l'escape della segreteria telefonica in Skype for Business](configure-voice-mail-escape.md)