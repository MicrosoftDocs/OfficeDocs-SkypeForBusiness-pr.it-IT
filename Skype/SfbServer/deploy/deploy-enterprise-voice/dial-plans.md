---
title: Creare o modificare un dial plan in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Riepilogo: informazioni su come creare o modificare un dial plan tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 456bd4c46b371da260340fab4e2b7152d14f7924
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240728"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Creare o modificare un dial plan in Skype for Business Server

**Riepilogo:** Informazioni su come creare o modificare un dial plan usando il pannello di controllo di Skype for Business Server.

### <a name="to-create-a-dial-plan"></a>Per creare un dial plan

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.

3. Nella pagina **dial plan** fare clic su **nuovo** e selezionare un ambito per il dial plan:

   - Il **dial plan di sito** si applica a un intero sito, eccetto gli utenti o i gruppi assegnati a un dial plan utente. Se si seleziona **sito** per l'ambito di un dial plan, è necessario scegliere il sito nella finestra di dialogo **Seleziona sito** . Se è già stato creato un dial plan per un sito, il sito non viene visualizzato nella finestra di dialogo **Seleziona sito** .

   - Il **dial plan per pool** può essere applicato a un gateway PSTN (Public Switched Telephone Network) o a un registrar. Se si seleziona **pool** per l'ambito di un dial plan, scegliere il gateway PSTN o il registrar nella finestra di dialogo **Seleziona servizio** . Se è già stato creato un dial plan per un servizio (gateway PSTN o registrar), il servizio non viene visualizzato nell'elenco.

   - Il **dial plan utente** può essere applicato agli utenti o ai gruppi specificati.

     > [!NOTE]
     > Dopo aver selezionato l'ambito del dial plan, non è possibile modificarlo.

4. Se si sta creando un piano di chiamata utente, immettere un nome descrittivo nel campo **nome** della finestra di dialogo **nuovo piano di chiamata** . Dopo aver salvato questo nome, non è possibile modificarlo.

    > [!NOTE]
    > Per i piani di chiamata del sito, il campo **nome** viene precompilato con il nome del sito e non può essere modificato. > per i piani di chiamata in pool, il campo **nome** viene precompilato con il nome del gateway o del registrar PSTN e non può essere modificato.

5. Il campo **nome semplice** viene prepopolato con lo stesso nome visualizzato nel campo **nome** . Facoltativamente, è possibile modificare questo campo per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.

   > [!IMPORTANT]
   > Il **nome semplice** deve essere univoco tra tutti i dial plan della distribuzione. Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.) o uno stato di sottolineatura (_). > i caratteri **non supportati** includono spazi e caratteri riservati<http://www.ietf.org/rfc/rfc3966.txt>come definito in RFC 3966 (). I caratteri riservati **non supportati** nel **nome semplice** includono i seguenti: > ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. Opzionale Nel campo **Descrizione** è possibile digitare ulteriori informazioni descrittive sul dial plan.

7. Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso. Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.

    > [!NOTE]
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.

8. Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna. È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri (#, * e 0-9).

    > [!NOTE]
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.

9. Associare e configurare le regole di normalizzazione per il dial plan nel modo seguente:

    - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole**di normalizzazione evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.

   - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [creare o modificare una regola di normalizzazione in Skype for business](normalization-rules.md).

   - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.

   - Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**.

   - Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.

     > [!NOTE]
     > Ogni dial plan deve avere almeno una regola di normalizzazione associata. Per informazioni su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere [pianificare il routing vocale in uscita in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) nella documentazione relativa alla pianificazione.

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.

    > [!IMPORTANT]
    > Skype for Business Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive. > l'impostazione predefinita **Mantieni tutte** le regole di normalizzazione ^ (\d{11}) $ corrisponde a qualsiasi numero di 11 cifre. Ad esempio, se si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che **Keep all** sia ordinato sotto la regola più restrittiva ^ (1425{7}\ d) $.

11. Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.

12. Fare clic su **OK**.

13. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea un dial plan, è necessario eseguire il comando **Commit all** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

### <a name="to-modify-a-dial-plan"></a>Per modificare un dial plan

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.

4. Nella pagina **dial plan** fare doppio clic su un nome di dial plan.

    > [!NOTE]
    > L'ambito e il nome del dial plan sono stati impostati quando è stato creato il dial plan. Non possono essere modificate.

5. Opzionale In **Modifica dial plan**modificare il campo **nome semplice** , che viene prepopolato con lo stesso nome visualizzato nel campo **nome** per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.

    > [!IMPORTANT]
    > Il **nome semplice** deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013. Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.), un segno di addizione (+) o uno stato di sottolineatura (_). > gli spazi non sono consentiti nel campo **nome semplice** .

6. Opzionale Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.

7. Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso. Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.

    > [!NOTE]
    > Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.

8. Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive per ottenere una linea esterna, ad esempio 9. È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri, ovvero #, * e 0-9.

    > [!NOTE]
    > Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.

9. Associare e configurare le regole di normalizzazione per il dial plan:

   - Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Nella finestra di dialogo **Seleziona regole** di normalizzazione evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.

   - Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [creare o modificare una regola di normalizzazione in Skype for business](normalization-rules.md).

   - Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.

   - Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**.

   - Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.

     > [!NOTE]
     > Ogni dial plan deve avere almeno una regola di normalizzazione associata. Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere [pianificare il routing vocale in uscita in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) nella documentazione relativa alla pianificazione.

10. Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.

    > [!IMPORTANT]
    > Skype for Business Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive. > l'impostazione predefinita **Mantieni tutte** le regole di normalizzazione ^ (\d{11}) $ corrisponde a qualsiasi numero di 11 cifre. Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che **Keep all** sia ordinato sotto la regola più restrittiva ^ (1425{7}\ d) $.

11. Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.

    > [!NOTE]
    > È possibile salvare un dial plan che non supera ancora il test e quindi riconfigurarlo in un secondo momento. Per informazioni dettagliate, vedere [test del routing vocale](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Fare clic su **OK**.

13. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando **Commit all** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

## <a name="see-also"></a>Vedere anche

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business](voice-route-config-changes.md)

