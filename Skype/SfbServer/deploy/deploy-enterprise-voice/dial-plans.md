---
title: Creare o modificare un dial plan in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Riepilogo: informazioni su come creare o modificare un dial plan utilizzando il Skype for Business Server di controllo.'
---

# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Creare o modificare un dial plan in Skype for Business Server

**Riepilogo:** Informazioni su come creare o modificare un dial plan utilizzando il Pannello Skype for Business Server di controllo.

### <a name="to-create-a-dial-plan"></a>Per creare un dial plan

1. Aprire Skype for Business Server Pannello di controllo.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.

3. Nella pagina **Dial plan** fare clic su **Nuovo** e selezionare un ambito per il dial plan:

   - **Dial plan sito** è applicabile a un intero sito, ad eccezione degli eventuali utenti o gruppi assegnati a un dial plan utente. Se si seleziona **Sito** per l'ambito di un dial plan, è necessario scegliere il sito nella **finestra di dialogo** Seleziona un sito. Se per un sito è stato già creato un dial plan, il sito non viene visualizzato nella finestra di dialogo **Seleziona un sito**.

   - **Dial plan pool** può essere applicabile a un gateway PSTN (Public Switched Telephone Network) o a una funzione di registrazione. Se si seleziona **Pool** per l'ambito di un dial plan, scegliere il gateway PSTN o la funzione di registrazione nella **finestra di dialogo Seleziona** un servizio. Se è stato già creato un dial plan per un servizio (gateway PSTN o funzione di registrazione), il servizio non viene visualizzato nell'elenco.

   - **Dial plan utente** può essere applicato a utenti o gruppi specificati.

     > [!NOTE]
     > Dopo aver selezionato l'ambito del dial plan, non è più possibile modificarlo.

4. Se si crea un dial plan utente, immettere un nome descrittivo nel campo **Nome** della finestra di dialogo **Nuovo dial plan**. Dopo aver salvato tale nome, non è più possibile modificarlo.

    > [!NOTE]
    > Per i dial plan del sito, il campo **Nome** è prepopolato con il nome del sito e non può essere modificato.> Per i dial plan del pool, il campo **Nome** è prepopolato con il gateway PSTN o il nome della funzione di registrazione e non può essere modificato.

5. Il campo **Nome semplice** viene prepopolato con lo stesso nome visualizzato nel campo **Nome**. Se si desidera, è possibile modificare il campo per specificare un nome più descrittivo che rifletta il sito, il servizio o l'utente al quale viene applicato il dial plan.

   > [!IMPORTANT]
   > Il **nome semplice** deve essere univoco tra tutti i dial plan della distribuzione. Non può superare i 256 caratteri Unicode, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.) o un carattere di sottolineatura (_). **> I caratteri** non supportati includono spazi e caratteri riservati come definito in RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>). I caratteri riservati **non supportati** nel **nome semplice** includono: > ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. (Facoltativo) Nel campo **Descrizione** è possibile digitare ulteriori informazioni descrittive sul dial plan.

7. (Facoltativo) Se si desidera utilizzare questo dial plan come area per i numeri di accesso esterno, specificare un'**Area conferenza telefonica con accesso esterno**. Se non si desidera utilizzare questo dial plan per i numeri di accesso esterno, lasciare vuoto il campo.

    > [!NOTE]
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri di accesso alla conferenza telefonica con accesso esterno a uno o più dial plan.

8. (Facoltativo) Nel campo **Prefisso accesso esterno** specificare un valore solo se gli utenti devono comporre una o più cifre iniziali aggiuntive, ad esempio 9, per accedere a una linea esterna. È possibile digitare un valore di prefisso con al massimo quattro caratteri (#, * e i numeri da 0 a 9).

    > [!NOTE]
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includerlo.

9. Associare e configurare le regole di normalizzazione per il dial plan nel modo seguente:

    - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e fare clic su **OK**.

   - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Nuova**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [Create or modify a normalization rule in Skype for Business](normalization-rules.md).

   - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.

   - Per copiare una regola di normalizzazione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **Copia** e quindi su **Incolla**.

   - Per rimuovere una regola di normalizzazione dal dial plan, evidenziarne il nome e fare clic su **Rimuovi**.

     > [!NOTE]
     > A ogni dial plan deve essere associata almeno una regola di normalizzazione. Per informazioni su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) nella documentazione relativa alla pianificazione.

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia su o giù.

    > [!IMPORTANT]
    > Skype for Business Server l'elenco delle regole di normalizzazione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano elencate prima di quelle meno restrittive. > La regola di normalizzazione **predefinita Mantieni** tutto^(\d{11})$ corrisponde a qualsiasi numero a 11 cifre. Ad esempio, se si aggiunge una regola di normalizzazione che corrisponde a numeri a 11 cifre che iniziano con 1425, assicurarsi che **l'opzione** Mantieni tutto sia ordinata al di sotto della regola più restrittiva^(1425\d{7})$.

11. (Facoltativo) Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero composto da testare**.

12. Fare clic su **OK**.

13. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea un dial plan, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

### <a name="to-modify-a-dial-plan"></a>Per modificare un dial plan

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.

2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.

4. Nella pagina **Dial plan** fare doppio clic sul nome di un dial plan.

    > [!NOTE]
    > L'ambito e il nome del dial plan sono stati impostati al momento della creazione del dial plan e non possono essere modificati.

5. (Facoltativo) In **Modifica dial plan** modificare il campo **Nome semplice**, in cui viene inserito automaticamente il nome visualizzato nel campo **Nome**, specificando un nome più descrittivo che rifletta il sito, il servizio o l'utente a cui si applica il dial plan.

    > [!IMPORTANT]
    > Il **nome semplice** deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013. Non può superare i 256 caratteri Unicode, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.), un segno più (+) o un carattere di sottolineatura (_).> Gli spazi non sono consentiti nel campo **Nome semplice.**

6. (Facoltativo) Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.

7. (Facoltativo) Se si desidera utilizzare questo dial plan come area per i numeri di accesso esterno, specificare un'**Area conferenza telefonica con accesso esterno**. Se non si desidera utilizzare questo dial plan per i numeri di accesso esterno, lasciare vuoto il campo.

    > [!NOTE]
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri di accesso alla conferenza telefonica con accesso esterno a uno o più dial plan.

8. (Facoltativo) Nel campo **Prefisso accesso esterno** specificare un valore solo se gli utenti devono comporre una o più cifre iniziali aggiuntive, ad esempio 9, per accedere a una linea esterna. È possibile digitare un valore di prefisso con al massimo quattro caratteri (#, * e i numeri da 0 a 9).

    > [!NOTE]
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includerlo.

9. Associare e configurare le regole di normalizzazione per il dial plan:

   - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Nella finestra di dialogo **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e fare clic su **OK**.

   - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Nuova**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [Create or modify a normalization rule in Skype for Business](normalization-rules.md).

   - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.

   - Per copiare una regola di normalizzazione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **Copia** e quindi su **Incolla**.

   - Per rimuovere una regola di normalizzazione dal dial plan, evidenziarne il nome e fare clic su **Rimuovi**.

     > [!NOTE]
     > A ogni dial plan deve essere associata almeno una regola di normalizzazione. Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere [Plan for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) nella documentazione relativa alla pianificazione.

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia su o giù.

    > [!IMPORTANT]
    > Skype for Business Server l'elenco delle regole di normalizzazione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano elencate prima di quelle meno restrittive. > La regola di normalizzazione **predefinita Mantieni** tutto^(\d{11})$ corrisponde a qualsiasi numero a 11 cifre. Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri a 11 cifre che iniziano con 1425, assicurarsi che **l'opzione** Mantieni tutto sia ordinata al di sotto della regola più restrittiva^(1425\d{7})$.

11. (Facoltativo) Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero composto da testare**.

    > [!NOTE]
    > È possibile salvare un dial plan che non ha superato ancora il test e quindi riconfigurarlo successivamente. Per informazioni dettagliate, vedere [Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

12. Fare clic su **OK**.

13. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business](voice-route-config-changes.md)