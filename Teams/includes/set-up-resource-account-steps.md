In Microsoft Teams, è necessario un account di risorsa per ogni operatore automatico o coda di chiamata. Agli account delle risorse possono essere assegnati anche numeri di telefono di servizio. Questo è il modo in cui assegni i numeri di telefono agli operatori automatici e alle code di chiamata consentendo ai chiamanti dall'esterno Teams di raggiungere l'operatore automatico o la coda di chiamata.

Questo articolo illustra come creare account delle risorse e prepararli per l'uso con gli operatori automatici e le code di chiamata.

Prima di iniziare le procedure descritte in questo articolo, assicurarsi di aver eseguito le operazioni seguenti:

- [Ottenere licenze utente virtuali](#obtain-virtual-user-licenses)
- [Ottenere i numeri di servizio](#obtain-service-numbers)

> [!NOTE]
> Gli account delle risorse utilizzati per gli operatori automatici e le code di chiamata sono disabilitati per l'accesso e devono rimanere tali. La chat e la presenza non sono disponibili per questi account.

### <a name="obtain-virtual-user-licenses"></a>Ottenere licenze utente virtuali

Ogni account delle risorse richiede una licenza per poter lavorare con gli operatori automatici e le code di chiamata. È possibile usare una licenza gratuita *Telefono di Microsoft Teams Standard - Utente virtuale*. Per ottenere queste licenze, vedere [Licenza utente virtuale](../teams-add-on-licensing/virtual-user.md).

Viene illustrato come [assegnare la licenza a un account delle risorse più avanti in questo articolo](#assign-a-license).

Se hai acquistato **Teams Phone Standard** o **Teams Telefono con licenze bundle piano per** chiamate, le licenze virtuali sono già presenti nel tuo account.

Per verificare se si hanno già licenze virtuali, accedere a Microsoft 365 usando un account con autorizzazioni di amministratore globale. Quindi, vai a [Fatturazione > i tuoi prodotti](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se si hanno licenze virtuali, verranno visualizzate come **Telefono di Microsoft Teams Standard - Utente virtuale**.

1. Aprire il interfaccia di amministrazione di Microsoft 365 e accedere con un utente amministratore globale. Si tratta in genere dell'account usato per iscriversi per Microsoft 365.
2. Nel riquadro di spostamento sinistro passare a **Componenti aggiuntivi** >  [**per l'acquisto** di **fatturazione** > ](https://admin.microsoft.com/Adminportal/Home#/catalog) > **Vedere tutti i prodotti componenti aggiuntivi**.
3. Scorrere fino alla fine per trovare la licenza **Telefono di Microsoft Teams Standard - Utente virtuale**. Seleziona **Dettagli**, quindi **Acquista**.
4. Nella pagina di acquisto della licenza selezionare il numero di licenze utente virtuali desiderate. È necessaria una licenza virtuale per ogni operatore automatico e coda di chiamata che si prevede di configurare. Ti consigliamo di selezionare almeno cinque licenze in modo da poter facilmente configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.
5. Deselezionare **Assegna automaticamente a tutti gli utenti senza licenza**.
6. Seleziona **Estrai ora**.
7. Conferma l'ordine, seleziona **Avanti** e quindi **Effettua ordine**.

Il costo è zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.

### <a name="obtain-service-numbers"></a>Ottenere i numeri di servizio

I numeri di servizio sono facoltativi per gli operatori automatici e le code di chiamata, tuttavia è necessario almeno un numero di servizio per consentire ai chiamanti di raggiungere la configurazione dell'operatore automatico e della coda di chiamata. Per qualsiasi operatore automatico o coda di chiamata che desideri essere raggiungibile direttamente da un numero di servizio, devi disporre di un account della risorsa con un numero di servizio associato.

Gli account delle risorse possono utilizzare numeri di servizio a pagamento o numeri verdi. Puoi richiedere nuovi numeri o trasferire numeri esistenti da un altro gestore telefonico.

Per ottenere nuovi numeri di servizio, vedi [Recupero di numeri di telefono di servizio](../getting-service-phone-numbers.md).

Per trasferire un numero da un altro gestore telefonico, vedi [Trasferire numeri di telefono a Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Creare un account di risorsa

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

1. Nell'interfaccia di amministrazione di Teams espandere **Voce** e quindi selezionare **Account delle risorse**.
2. Selezionare **Aggiungi**.
3. Nel riquadro **Aggiungi account risorsa** compilare **Nome visualizzato**, **Nome utente** e **tipo di account risorsa**. Il tipo di account della risorsa può essere **Operatore automatico** o **Coda di chiamata**, a seconda di come si prevede di utilizzare questo account della risorsa.
4. Selezionare **Salva**.

## <a name="assign-a-license"></a>Assegnare una licenza

Per ogni account delle risorse, è necessario assegnare una licenza *Telefono di Microsoft Teams Standard - Utente virtuale* o *Teams Phone Standard* licenza.

1. Nel interfaccia di amministrazione di Microsoft 365 espandere **Utenti**, quindi selezionare **Utenti attivi**.
2. Selezionare l'account della risorsa a cui si vuole assegnare una licenza. Verrà visualizzato il riquadro utente dell'account delle risorse.
3. Nella scheda **Licenze e app**, in **Licenze**, selezionare **Telefono di Microsoft Teams Standard - Utente virtuale**.
4. Selezionare **Salva modifiche**.

## <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se si prevede di usare l'account della risorsa con un operatore automatico o una coda di chiamata che richiede un numero di servizio, assegnare un numero all'account della risorsa.

1. Nella pagina **Account risorsa** dell'interfaccia di amministrazione di Teams selezionare l'account della risorsa a cui si vuole assegnare un numero di servizio e quindi selezionare **Assegna/annulla assegnazione**.
2. Nell'elenco a discesa **Telefono tipo di numero** scegliere il tipo di numero da usare.
3. Nella casella **Numero di telefono assegnato** cerca il numero che vuoi usare e seleziona **Aggiungi**. Assicurarsi di includere il codice paese (ad esempio + 1 250 555 0012).
4. Selezionare **Salva**.

Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell:

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`