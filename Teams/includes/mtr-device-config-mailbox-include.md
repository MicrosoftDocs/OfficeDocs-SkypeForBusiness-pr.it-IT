
È possibile migliorare l'esperienza di Teams Rooms riunione personalizzando il modo in cui l'account della risorsa risponde e elabora gli inviti alle riunioni. Usando Exchange Online PowerShell, è possibile impostare le proprietà dell'account delle risorse seguenti:

- **Automateprocessing: `AutoAccept`** Gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza intervento umano.

- **AddOrganizerToSubject: `$false`** L'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione.

- **DeleteComments: `$false`** Mantenere il testo nel corpo del messaggio delle convocazioni riunione in arrivo. Questa operazione è necessaria per elaborare le riunioni esterne di Teams e di terze parti per offrire un'esperienza Di partecipazione tramite tocco.

- **DeleteSubject: `$false`** Mantenere l'oggetto delle convocazioni riunione in arrivo.

- **ProcessExternalMeetingMessages: `$true`** Specifica se elaborare le convocazioni riunione provenienti dall'esterno dell'organizzazione di Exchange. Obbligatorio per le riunioni esterne di Teams e [di terze parti](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga quello specificato.

- **AddAdditionalResponse: `$true`** Il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione.

- **AdditionalResponse: "Questa è una sala riunioni di Microsoft Teams!"** Testo aggiuntivo da aggiungere alla risposta di accettazione riunione.

Per configurare queste proprietà, è necessario connettersi a Exchange Online PowerShell. Per altre informazioni, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

Dopo essersi connessi a Exchange Online PowerShell, è possibile configurare le proprietà della cassetta postale in un account di risorsa usando il cmdlet [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

L'esempio seguente imposta le proprietà per l'account della `ConferenceRoom01` risorsa:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

