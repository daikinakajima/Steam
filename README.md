# SteamAPIの使い方

SteamAPIを使うと、そのプラットホーム上の情報を取得することができる。

## Step1()

http://steamcommunity.com/login/home/ でSteamのアカウントを作成する。

http://steamcommunity.com/dev/apikey/ でドメイン名を入れてAPIキーを取得する。

## Step2()

## Step3()

## Step4()

# SteamAPIでできること

**・GetNewsForApp（v0002）**
GetNewsForAppは、そのappIDで指定されたゲームの最新のニュースを返します。

**・GetGlobalAchievementPercentagesForApp（v0002）  **
特定のゲームのグローバル実績の概要をパーセンテージで返します。

・GetGlobalStatsForGame（v0001）  
ゲームのグローバル統計を取得する。

・GetPlayerSummaries（v0002）  
プレイヤーの概要を取得する

### 公開データ
・steamids  
64ビットユーザーのSteamID

・personaname  
プレイヤの表示名。

・profileurl  
プレイヤーのSteamコミュニティプロフィールの完全なURL。
・avatar  
・プレーヤーの32x32pxアバターの完全なURL。
・avatarmedium  
プレーヤーの64x64pxアバターの完全なURL。
・avatarfull  
プレーヤーの184x184pxアバターの完全なURL。

・personastate  
ユーザーの現在のステータス。  
0-オフライン、1-オンライン、2-ビジー、3-アウェイ、4-スヌーズ、5-見栄え、6-遊びたい。
プレーヤーのプロフィールがプライベートの場合、バグによりプロフィールがプライベートであってもそれらのステータスが表示されるため、ユーザーが自分のステータスをトレードしようとする、またはプレイするように設定している場合を除き、これは常に「0」になります。

・communityvisibilitystate  
これは、プロファイルが表示されているかどうかを示し、表示されている場合は、そのプロファイルが表示される理由を示します。このWebAPIは認証を使用しないため、返される可能性のある値は2つだけです：1-プロファイルがあなたには見えない（Private、FriendsOnlyなど）、3-プロファイルが"Public"であり、データが見える。MikeBlaszczakのSteamフォーラムの記事では、「このAPIが返すコミュニティの可視性の状態はプライバシーの状態とは異なります。リクエストされたアカウントと表示されたアカウントとの関係から見たアカウントへのリクエストからアカウントへの有効な可視状態です。

・profilestate  
設定されている場合、ユーザーにコミュニティプロフィールが設定されていることを示します（'1'に設定されます）。

・lastlogoff  
ユーザーがオンラインであった最後の時間（UNIX時間）。

・commentpermission  
設定されている場合、プロファイルが公開コメントを許可することを示します。

### 私的なデータ
・realname  
プレーヤーの実名。

・primaryclanid  
Steamコミュニティプロフィールで設定されているプレイヤーのプライマリグループ。

・timecreated  
プレーヤーのアカウントが作成された時刻。

・gameid  
ユーザーが現在ゲーム中の場合、この値が返され、そのゲームのgameidに設定されます。

・gameserverip  
スチームマッチメイキングを使用してゲームでオンラインでプレイしている場合、ユーザーが現在プレイしているゲームサーバーのIPとポート。それ以外の場合は「0.0.0.0:0」に設定されます。

・gameextrainfo  
ユーザーが現在ゲーム中の場合、これはプレイしているゲームの名前になります。これはSteam以外のゲームのショートカットの名前である可能性があります。

・loccountrycode  
ユーザーのSteamコミュニティプロフィールに設定されている場合、ユーザーの居住国、2文字のISO国コード
・locstatecode  
ユーザーのSteamコミュニティプロフィールに設定されている場合、ユーザーの居住状態

・GetFriendList（v0001）  
Steamコミュニティプロフィールの表示設定が「公開」に設定されている場合、すべてのSteamユーザーのフレンドリストを返します。

### 結果データ
ユーザーの友人リストは、友人の配列として表示されます。プロフィールが非公開の場合は何も返されません。

・steamid  
友人の64ビットスチームID。

・relationship  
フレンドとの関係。

・friend_since  
関係が作成された時刻のUnixタイムスタンプ。

GetPlayerAchievements（v0001）
GetUserStatsForGame（v0002）
GetOwnedGames（v0001）
GetRecentlyPlayedGames（v0001）
IsPlayingSharedGame（v0001）
GetSchemaForGame（v2）
GetPlayerBans（v1）
