
Per aiutare gli utenti a pianificare più facilmente riunioni in una sala riunioni di Teams, è possibile creare elenchi di sale e luoghi in Exchange Online. 

Gli elenchi delle chat room di Exchange e le posizioni di Outlook vengono usati per controllare gli account delle risorse (e quindi i Teams Rooms a cui sono associati) visualizzati in Ricerca sala di Outlook. Ricerca sala è una funzionalità di Outlook che consente agli utenti di trovare le sale vicine, disponibili per la prenotazione e che soddisfano altri criteri, ad esempio la disponibilità di uno schermo.

Gli elenchi di sale sono un tipo speciale di gruppo di distribuzione di Exchange che consente di raggruppare in modo significativo gli account delle risorse (e quindi i Teams Rooms a cui sono associati). Ad esempio, è possibile creare elenchi di sale per tutte le sale di ogni edificio del campus.

Outlook Places consente di impostare attributi specifici per un account di risorsa e per la sala riunioni di Teams. Alcuni degli attributi che è possibile impostare sono:

- Edificio
- Città
- Capacità
- Se la posizione è accessibile in sedia a rotelle
- Nomi audio, video e visualizzati

Usando una combinazione di elenchi di sale e attributi di luogo selezionati da un utente, Ricerca sala in Outlook mostrerà un elenco di sale disponibili per la prenotazione. Per usare al meglio gli elenchi e le posizioni delle sale, creare elenchi di sale in base a un attributo place, ad esempio building. Ad esempio, impostare gli attributi città e luogo di costruzione per ogni account della risorsa e quindi aggiungere ogni account della risorsa a un elenco di sale riunioni. Quando un utente prova a scegliere una sala da prenotare, Outlook visualizza un elenco di città e gli elenchi di sale disponibili in ognuna di queste città.

> [!IMPORTANT]
> Ogni account della risorsa deve avere gli attributi di posizione impostati. Se questi attributi, in particolare città, edificio e capacità, non sono impostati, tali camere non verranno visualizzate come opzioni disponibili per la prenotazione anche se un elenco di camere li contiene.

Per creare un elenco di chat room, seguire le istruzioni in [Creare un elenco chat room](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

Per configurare gli attributi di posizione per un account delle risorse, vedere [Set-Place](/powershell/module/exchange/set-place).
