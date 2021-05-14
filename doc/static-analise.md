# Statikus analízis

Alapvetően két különböző eszközt használtunk az analízis során.

## SonarLint

Kezdetben 15 hibát észlelt az eszköz. Ezen hibák közül egyik sem volt súlyosnak mondható, inkább javaslatokat tett ésszerűbb megvalósítások használatára. A Java nyelvből ismert System.out-ot logger funkcióra cseréltetné, több helyen dedikált kivételt dobna beépített helyett, illetve elnevezési módosításokat javasolt. Ezek közül párat felvettünk GitHubra issue-ként.
