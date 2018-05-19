# posts

## Description



## Columns

| Name | Type | Default | NOT NULL | Comment |
| ---- | ---- | ------- | -------- | ------- |
| id | bigint | nextval('posts_id_seq'::regclass) | true |  |
| user_id | integer |  | true |  |
| title | varchar(255) |  | true |  |
| body | text |  | true |  |
| post_type | post_types |  | true | public/private/draft |
| labels | array |  | false |  |
| created | timestamp without time zone |  | true |  |
| updated | timestamp without time zone |  | false |  |

## Constraits

| Name | Def |
| ---- | --- |
| posts_id_pk | PRIMARY KEY (id) |
| posts_user_id_fk | FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE |

## Indexes

| Name | Def |
| ---- | --- |
| posts_id_pk | CREATE UNIQUE INDEX posts_id_pk ON public.posts USING btree (id) |
| posts_user_id_idx | CREATE INDEX posts_user_id_idx ON public.posts USING btree (user_id) |

---

> Generated by [tbls](https://github.com/k1LoW/tbls)