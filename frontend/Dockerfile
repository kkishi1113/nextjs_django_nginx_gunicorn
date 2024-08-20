# ベースイメージとしてNode.jsを使用
FROM node:18-alpine

# 作業ディレクトリを作成
WORKDIR /usr/src/app

# RUN npx create-next-app@latest my-app --ts --tailwind --eslint --no-src-dir --no-app --import-alias '@/*'

# package.jsonとpackage-lock.jsonをコピー
COPY package*.json ./

# 依存関係をインストール
RUN npm install

# ソースコードをコピー
COPY . .

# Next.jsのビルド
RUN npm run build

# 開発サーバを起動
CMD ["npm", "run", "dev"]

# ポート3000を公開
EXPOSE 3001
