In Microsoft Teams è necessario un account di risorsa per ogni operatore automatico o coda di chiamata. Agli account delle risorse possono essere assegnati anche numeri di telefono. È così che si assegnano numeri di telefono agli operatori automatici e alle code di chiamata, consentendo ai chiamanti esterni a Teams di raggiungere l'operatore automatico o la coda di chiamata.

Questo articolo illustra come creare account delle risorse e prepararli per l'uso con gli operatori automatici e le code di chiamata.

Prima di iniziare le procedure descritte in questo articolo, assicurarsi di aver eseguito le operazioni seguenti:

- [Ottenere licenze per Telefono di Microsoft Teams account delle risorse](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Ottenere numeri di telefono](#obtain-phone-numbers)

> [!NOTE]
> Gli account delle risorse utilizzati per gli operatori automatici e le code di chiamata sono disabilitati per l'accesso e devono rimanere tali. La chat e la presenza non sono disponibili per questi account.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Ottenere licenze per Telefono di Microsoft Teams account delle risorse

Ogni account delle risorse richiede una licenza per poter lavorare con gli operatori automatici e le code di chiamata, nota come **licenza account di risorsa Telefono di Microsoft Teams**. Gli abbonamenti con Teams Phone ottengono automaticamente un'allocazione gratuita di licenze per **Telefono di Microsoft Teams account risorse** e, se ne servono altre, è possibile acquistare licenze aggiuntive **Telefono di Microsoft Teams account risorse**. Per informazioni dettagliate su come ottenere queste licenze, vedere [Telefono di Microsoft Teams licenze account risorse](../teams-add-on-licensing/virtual-user.md).

Viene illustrato come [assegnare la licenza a un account delle risorse più avanti in questo articolo](#assign-a-license).

Se hai acquistato **Teams Phone Standard** o **Teams Phone con licenze bundle per il piano per** chiamate, le licenze **per l'account di Teams Phone Resource** sono già presenti nel tuo account.

Per vedere se si hanno già licenze **per l'account di risorse di Teams Phone**, accedere al [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) usando un account con autorizzazioni di amministratore globale. Quindi, vai a [Fatturazione > i tuoi prodotti](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se si hanno licenze **per l'account di risorse di Teams Phone**, verranno visualizzate come **Telefono di Microsoft Teams account di risorsa**.

1. Aprire il [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) e accedere con un utente amministratore globale. Si tratta in genere dell'account usato per iscriversi a Microsoft 365.
2. Nel riquadro di spostamento sinistro passare a **Componenti aggiuntivi** >  [**per l'acquisto** di **fatturazione** > ](https://admin.microsoft.com/Adminportal/Home#/catalog) > **Vedere tutti i prodotti componenti aggiuntivi**.
3. Scorrere fino alla fine per trovare la licenza **Telefono di Microsoft Teams Account risorse**. Seleziona **Dettagli**, quindi **Acquista**.
4. Nella pagina di acquisto della licenza selezionare il numero di licenze desiderato. È necessaria una licenza per ogni operatore automatico e coda di chiamata che si prevede di configurare. Ti consigliamo di selezionare almeno cinque licenze in modo da poter facilmente configurare più operatori automatici e code di chiamata in futuro senza dover acquistare subito altre licenze.
5. Deselezionare **Assegna automaticamente a tutti gli utenti senza licenza**.
6. Seleziona **Estrai ora**.
7. Conferma l'ordine, seleziona **Avanti** e quindi **Effettua ordine**.

Il costo è zero, ma è comunque necessario seguire questa procedura per acquisire la licenza.

### <a name="obtain-phone-numbers"></a>Ottenere numeri di telefono

I numeri di telefono sono facoltativi per gli operatori automatici e le code di chiamata. Per qualsiasi operatore automatico o coda di chiamata che desideri essere raggiungibile direttamente da un numero di telefono, devi disporre di un account di risorse con un numero di telefono associato.

Gli account delle risorse possono utilizzare numeri verdi o a pagamento. Puoi richiedere nuovi numeri o trasferire numeri esistenti da un altro gestore telefonico.

I numeri di telefono accettabili che possono essere applicati agli account delle risorse includono:

- **Numeri di servizio piani per chiamate:** Per acquisire numeri di servizio con Piani per chiamate, vedi [Recupero di numeri di telefono di servizio](../getting-service-phone-numbers.md).
- **Numeri di routing diretto:** Per acquisire numeri di routing diretto, vedere [Abilitare gli utenti per il routing diretto](/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice).
- **Numeri di connessione operatore:** Per acquisire numeri operator connect, vedi [Configurare Operator Connect](/microsoftteams/operator-connect-configure#set-up-phone-numbers).

Per trasferire un numero da un altro gestore telefonico, vedi [Trasferire numeri di telefono in Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Creare un account di risorsa

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

1. Accedere [all'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). 
2. Espandi **Voce** e quindi seleziona **Account delle risorse**.
3. Selezionare **Aggiungi**.
4. Nel riquadro **Aggiungi account risorsa** compilare **Nome visualizzato**, **Nome utente** e **tipo di account risorsa**. Il tipo di account della risorsa può essere **Operatore automatico** o **Coda di chiamata**, a seconda di come si prevede di utilizzare questo account della risorsa.
5. Selezionare **Salva**.

## <a name="assign-a-license"></a>Assegnare una licenza

Per ogni account della risorsa, è necessario assegnare una licenza **Telefono di Microsoft Teams Account risorse**.

1. Accedi alla [interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). 
2. Espandere **Utenti**, quindi selezionare **Utenti attivi**.
3. Selezionare l'account della risorsa a cui si vuole assegnare una licenza. Verrà visualizzato il riquadro utente dell'account delle risorse.
4. Nella scheda **Licenze e app**, in **Licenze**, selezionare **Telefono di Microsoft Teams account di risorse**.
5. Selezionare **Salva modifiche**.

## <a name="assign-a-phone-number"></a>Assegnare un numero di telefono

Se prevedi di usare l'account della risorsa con un operatore automatico o una coda di chiamata che richiede un numero di telefono, assegna un numero all'account della risorsa.

1. Accedere [all'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Espandi **Voce** e quindi seleziona **La pagina Account delle risorse** .
3. Selezionare l'account della risorsa a cui si vuole assegnare un numero di telefono e quindi selezionare **Assegna/annulla assegnazione**.
4. Nell'elenco a discesa **Tipo di numero di telefono** scegliere il tipo di numero da usare.
5. Nella casella **Numero di telefono assegnato** cerca il numero che vuoi usare e seleziona **Aggiungi**. Assicurarsi di includere il codice paese (ad esempio + 1 250 555 0012).
6. Selezionare **Salva**.

Per assegnare un routing diretto o un numero ibrido a un account di risorse, è necessario usare PowerShell:

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```
