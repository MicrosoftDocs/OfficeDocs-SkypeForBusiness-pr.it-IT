---
title: Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Riepilogo: creare o modificare i criteri vocali e configurare i record di utilizzo PSTN tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: b9024ea1efac7f58fea7175f22f85b325ab5a43c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195202"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business

**Riepilogo:** Creare o modificare i criteri vocali e configurare i record di utilizzo PSTN tramite il pannello di controllo di Skype for Business Server.

> [!NOTE]
> Ogni criterio vocale deve avere almeno un record di utilizzo PSTN (Public Switched Telephone Network) associato. Per visualizzare un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale e visualizzare le relative proprietà, vedere [visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Per creare un criterio vocale

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **criteri vocali**.

3. Nella pagina **criteri vocali** fare clic su **nuovo** e quindi selezionare un ambito per il nuovo criterio:

   - I **criteri del sito** si applicano a un intero sito, eccetto gli utenti o i gruppi assegnati a un criterio utente. Se si seleziona sito per un ambito di criteri, scegliere il sito nella finestra di dialogo **Seleziona sito** . Se è già stato creato un criterio vocale per un sito, il sito non viene visualizzato nella finestra di dialogo **Seleziona sito** .

   - I **criteri utente** possono essere applicati agli utenti o ai gruppi specificati.

4. Se l'ambito dei criteri vocali è un utente, immettere un nome descrittivo per i criteri nel campo **nome** .

    > [!NOTE]
    > Se l'ambito dei criteri vocali è sito, il campo **nome** nei **nuovi criteri vocali** viene precompilato con il nome del sito e non può essere modificato.

5. Opzionale Immettere altre informazioni descrittive per il criterio vocale.

6. Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ogni **funzionalità di chiamata** per il criterio vocale:

   - La funzionalità **escape** per la segreteria telefonica impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata.

     > [!NOTE]
     > Questa caratteristica può essere configurata solo tramite Skype for Business Server Management Shell

   - L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client. Skype for Business Server offre una gamma di opzioni di configurazione molto più ampia per l'inoltro di chiamata. Ad esempio, se un'organizzazione non vuole consentire la trasmissione esterna delle chiamate in arrivo alla rete PSTN, un amministratore può applicare un criterio vocale speciale per distribuire questa restrizione. Abilitato per impostazione predefinita.

   - La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto. In Skype for Business Server, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al suo manager di chiamare tutti gli obiettivi di chiamata simultanea del delegato. In questo modo il delegato offre maggiore flessibilità per rispondere alle chiamate indirizzate al responsabile. Abilitato per impostazione predefinita.

   - Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti. Abilitato per impostazione predefinita.

   - **Call Park** consente agli utenti di parcheggiare le chiamate in attesa e quindi prendere la chiamata da un altro telefono o client. Disabilitata per impostazione predefinita.

   - La **chiamata simultanea** consente alle chiamate in arrivo di squillare su altri telefoni (ad esempio, un cellulare) o altri dispositivi endpoint. Skype for Business Server offre una gamma molto più ampia di opzioni di configurazione per la chiamata simultanea. Abilitato per impostazione predefinita.

   - La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team. Abilitato per impostazione predefinita.

   - La reinstradazione **PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti dell'organizzazione di essere reinstradati sulla rete PSTN se la rete WAN è congestionata o non disponibile. Abilitato per impostazione predefinita.

   - **L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni sui criteri di controllo ammissione chiamata per un determinato utente. Disabilitata per impostazione predefinita.

     > [!NOTE]
     > Il criterio verrà ignorato solo per le chiamate in arrivo all'utente e non per le chiamate in uscita poste dall'utente. Una volta stabilita la sessione, il consumo di larghezza di banda verrà accuratamente registrato. Questa impostazione deve essere usata con parsimonia e deve essere riservata alle decisioni appropriate per il controllo dell'ammissione alle chiamate.

   - La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite (ad esempio minacce) usando l'interfaccia utente del client, che a sua volta contrassegna le chiamate nei record dettagli chiamata (CDRs). Disabilitata per impostazione predefinita.

   - Le **Opzioni di occupato** attivano o disabilitano le opzioni di occupato per il criterio vocale specificato. Le opzioni di occupato consente alle chiamate in arrivo di essere indirizzate alla segreteria telefonica o rifiutate con un segnale di occupato quando l'utente di destinazione della chiamata è al telefono. Opzioni di occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016. Il controllo di questo parametro consente di abilitare le opzioni di occupato e deselezionare Disabilita le opzioni di occupato. Per altre informazioni, Vedi [pianificare le opzioni di occupato per Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) e [installare e configurare le opzioni di occupato per Skype for Business Server](install-and-configure-busy-options.md).

7. Per associare e configurare i record di utilizzo PSTN per questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per scegliere uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare a questo criterio vocale e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN da questo criterio vocale, evidenziare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo a questo criterio vocale, eseguire le operazioni seguenti:

     un. Fare clic su **nuovo**.

     b. Nel campo **nome** immettere un nome descrittivo univoco per il record. Ad esempio, potresti voler creare un record di utilizzo PSTN namedRedmond per i dipendenti a tempo pieno che si trovano a Redmond e un altro namedRedmondTemps per i dipendenti temporanei.

     > [!NOTE]
     > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato.

     c. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     3D. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:

     un. Evidenziare il record di utilizzo PSTN che si vuole modificare e quindi fare clic su **Mostra dettagli**.

     b. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e Lick **show**details.

     c. Fare clic su **OK**.

8. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.

    > [!IMPORTANT]
    > L'ordine in cui i record di utilizzo PSTN sono elencati nel criterio vocale è significativo. Skype for Business Server attraversa l'elenco dall'alto verso il basso. Ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Per associare e configurare i record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per usare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo come criterio vocale, selezionare la route di opzione **usando gli utilizzi PSTN chiamata** dal menu a discesa.

   - Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Skype for business, selezionare l'opzione **Route per gli utenti di Skype for business interni solo** dal menu a discesa. Le chiamate non verranno inoltrate ai numeri PSTN esterni.

   - Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo di quello usato per questo criterio vocale, selezionare la route di opzione **usando gli usi PSTN personalizzati** dal menu a discesa. Questa opzione Visualizza un controllo per selezionare i record di utilizzo PSTN esistenti o creare nuovi record di utilizzo PSTN in modo specifico per l'inoltro di chiamata e lo squillo simultaneo.

   - Per scegliere uno o più record da un elenco di record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri di inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN da questo inoltro di chiamata e dal criterio di squillo simultaneo, evidenziare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri di inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:

     un. Fare clic su **nuovo**.

     b. Nel campo **nome** immettere un nome descrittivo univoco per il record.

     > [!NOTE]
     > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato.

     c. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     3D. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:

     un. Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.

     b. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

10. Opzionale Immettere un numero per testare il criterio vocale e fare clic su **Vai**. I risultati del test vengono visualizzati in **numero tradotto per il test**.

11. Fare clic su **OK**.

12. Nella pagina **criteri vocali** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

13. Opzionale La funzionalità di escape della segreteria telefonica rileva che una chiamata è stata immediatamente risolta dalla segreteria telefonica dell'utente e disconnette la chiamata alla segreteria telefonica per dispositivi mobili. In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente dando all'utente la possibilità di rispondere alla chiamata. Per informazioni dettagliate su come configurare un criterio per la segreteria telefonica, vedere [configurare l'escape della segreteria telefonica in Skype for business](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Per modificare un criterio vocale

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **criteri vocali**.

3. Nella pagina **criteri vocali** fare doppio clic su un nome di criterio vocale.

    > [!NOTE]
    > L'ambito e il nome sono stati impostati quando è stato creato il criterio vocale. Non possono essere modificate.

4. Opzionale In **modifica criterio vocale**immettere altre informazioni descrittive per il criterio vocale.

5. Selezionare o deselezionare le caselle di controllo seguenti per abilitare o disabilitare ognuna delle **funzionalità di chiamata**:

   - La funzionalità **escape** per la segreteria telefonica impedisce che le chiamate vengano immediatamente indirizzate al sistema di segreteria telefonica dell'utente quando è configurato lo squillo simultaneo e che il telefono sia disattivato, fuori batteria o fuori portata.

     > [!NOTE]
     > Questa caratteristica può essere configurata solo tramite Skype for Business Server Management Shell

   - L' **inoltro di chiamata** consente agli utenti di inoltrare le chiamate ad altri telefoni e dispositivi client. Skype for Business Server offre una gamma di opzioni di configurazione molto più ampia per l'inoltro di chiamata. Ad esempio, se un'organizzazione non vuole consentire la trasmissione esterna delle chiamate in arrivo alla rete PSTN, un amministratore può applicare un criterio vocale speciale per distribuire questa restrizione. Abilitato per impostazione predefinita.

   - La **delega** consente agli utenti di specificare ad altri utenti di inviare e ricevere chiamate per proprio conto. In Skype for Business Server, un delegato può configurare lo squillo simultaneo che consente alle chiamate in arrivo al suo manager di chiamare tutti gli obiettivi di chiamata simultanea del delegato. In questo modo il delegato offre maggiore flessibilità per rispondere alle chiamate indirizzate al responsabile. Abilitato per impostazione predefinita.

   - Il **trasferimento** delle chiamate consente agli utenti di trasferire le chiamate ad altri utenti. Abilitato per impostazione predefinita.

   - **Call Park** consente agli utenti di parcheggiare le chiamate in attesa e quindi di ritirare la chiamata da un altro telefono o client. Disabilitata per impostazione predefinita.

   - La **chiamata simultanea** consente alle chiamate in arrivo di squillare su altri telefoni (ad esempio, un cellulare) o altri dispositivi endpoint. Skype for Business Server offre una gamma molto più ampia di opzioni di configurazione per la chiamata simultanea. Abilitato per impostazione predefinita.

   - La **chiamata del team** consente agli utenti di un team definito di rispondere alle chiamate per gli altri membri del team. Abilitato per impostazione predefinita.

   - La reinstradazione **PSTN** consente alle chiamate effettuate dagli utenti a cui è assegnato questo criterio ad altri utenti dell'organizzazione di essere reinstradati sulla rete PSTN se la rete WAN è congestionata o non disponibile. Abilitato per impostazione predefinita.

   - **L'override dei criteri di larghezza di banda** consente agli amministratori di ignorare le decisioni del criterio CAC per un determinato utente. Disabilitata per impostazione predefinita.

     > [!NOTE]
     > Il criterio verrà ignorato solo per le chiamate in arrivo all'utente e non per le chiamate in uscita poste dall'utente. Una volta stabilita la sessione, il consumo di larghezza di banda verrà accuratamente registrato. Questa impostazione deve essere usata con parsimonia.

   - La **traccia di chiamata** non consentita consente agli utenti di segnalare chiamate illecite (ad esempio minacce) usando l'interfaccia utente del client, che a sua volta contrassegna le chiamate in CDRS. Disabilitata per impostazione predefinita.

6. Per associare e configurare i record di utilizzo PSTN per questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per scegliere uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare a questo criterio vocale e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN da questo criterio vocale, evidenziare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo a questo criterio vocale, eseguire le operazioni seguenti:

     un. Fare clic su **nuovo**.

     b. Nel campo **nome** immettere un nome descrittivo univoco per il record. Ad esempio, potresti voler creare un record di utilizzo PSTN namedRedmond per i dipendenti a tempo pieno che si trovano a Redmond e un altro record namedRedmondTemps per i dipendenti temporanei.

     > [!NOTE]
     > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato.

     c. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     3D. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:

     un. Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.

     b. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

7. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.

    > [!NOTE]
    > L'ordine in cui i record di utilizzo PSTN sono elencati nel criterio vocale è significativo. Skype for Business Server attraversa l'elenco dall'alto verso il basso. Ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Per associare e configurare i record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo in questo criterio vocale, eseguire una delle operazioni seguenti:

   - Per usare gli stessi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo come criterio vocale, selezionare la route di opzione **usando gli utilizzi PSTN chiamata** dal menu a discesa.

   - Per consentire l'inoltro di chiamata e lo squillo simultaneo solo agli utenti interni di Skype for business, selezionare **instrada agli utenti di Skype for business interni solo** dal menu a discesa. Le chiamate non verranno inoltrate ai numeri PSTN esterni.

   - Per specificare diversi record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo rispetto a quelli usati per questo criterio vocale, selezionare la route di opzione **usando gli usi PSTN personalizzati** dal menu a discesa. Questa opzione consente di visualizzare un controllo per selezionare i record di utilizzo PSTN esistenti o per creare nuovi record di utilizzo PSTN, in particolare per l'inoltro di chiamata e lo squillo simultaneo.

   - Per scegliere uno o più record da un elenco di record di utilizzo PSTN per l'inoltro di chiamata e lo squillo simultaneo, fare clic su **Seleziona**. Evidenziare i record che si desidera associare ai criteri di inoltro di chiamata e squillo simultaneo e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN da questo inoltro di chiamata e dal criterio di squillo simultaneo, evidenziare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo ai criteri di inoltro di chiamata e squillo simultaneo, eseguire le operazioni seguenti:

     un. Fare clic su **nuovo**.

     b. Nel campo **nome** immettere un nome descrittivo univoco per il record.

     > [!NOTE]
     > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato.

     c. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

   - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

   - Per rimuovere una route dal record utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

   - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

   - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     3D. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato a questo criterio vocale, eseguire le operazioni seguenti:

     un. Evidenziare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.

     b. Usare uno dei metodi seguenti per associare e configurare le route per questo record di utilizzo PSTN:

     - Per scegliere una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**, evidenziare le route da associare al record di utilizzo PSTN e quindi fare clic su **OK**.

     - Per rimuovere una route da questo record di utilizzo PSTN, evidenziare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla a questo record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

     - Per modificare una route già associata a questo record di utilizzo PSTN, evidenziare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Fare clic su **OK**.

9. Opzionale Immettere un numero per testare il criterio vocale e fare clic su **Vai**. I risultati del test vengono visualizzati in **numero tradotto per il test**.

10. Fare clic su **OK**.

11. Nella pagina **criteri vocali** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica un criterio vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

12. Opzionale La funzionalità di escape della segreteria telefonica rileva che una chiamata è stata immediatamente risolta dalla segreteria telefonica dell'utente e disconnette la chiamata alla segreteria telefonica per dispositivi mobili. In questo modo la chiamata continuerà a squillare sugli altri endpoint dell'utente dando all'utente la possibilità di rispondere alla chiamata. Per informazioni dettagliate su come configurare un criterio per la segreteria telefonica, vedere [configurare l'escape della segreteria telefonica in Skype for business](configure-voice-mail-escape.md).

## <a name="see-also"></a>Vedere anche

[Visualizzare i record di utilizzo PSTN in Skype for business](view-pstn-usage-records.md)

[Creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md)

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business](voice-route-config-changes.md)

[Configurare l'escape della segreteria telefonica in Skype for business](configure-voice-mail-escape.md)

