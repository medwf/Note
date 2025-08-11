# install setup
1. install in dev mode .
``` bash
# installed
npm i -D prisma

# initialized
npx prisma init
```

# Configure connection
2. open file `schema.prisma` : 
``` ts

datasource db {
	// choose provider postgres, mysql  ... 
	  provider = "mysql"
	  url      = env("DATABASE_URL")
}

// create models.
```

3. update `DATABASE_URL` connector in `.env`. 
	- `DATABASE_URL="mysql://<user>:<pass>@localhost:<port>/<db>?schema=public"`
# make database
# migrate
- change from code Prisma to actual database.
``` shell
# initialized database
npx prisma migrate dev --name init
```