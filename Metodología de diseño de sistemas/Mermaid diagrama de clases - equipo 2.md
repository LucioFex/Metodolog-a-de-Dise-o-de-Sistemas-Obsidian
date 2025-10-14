
```bash
classDiagram

class Usuario {
  +bigint usuario_id
  +varchar email
  +varchar nombreCompleto
  +char rol
  +text bio
  +varchar avatar_url
  -bytes password_hash
  +timestamptz creado_en
  +timestamptz actualizado_en
  --
  +registrarse(email, password, rol)
  +iniciarSesion(email, password)
  +editarPerfil(bio, avatarUrl)
  +unirseComunidad(comunidadId)
  +salirComunidad(comunidadId)
  +crearPost(comunidadId, titulo, cuerpo)
  +comentar(postId, parentId, texto)
  +votarPost(postId, valor)
  +votarComentario(comentarioId, valor)
  +guardarPost(postId)
  +quitarGuardado(postId)
}

class PreferenciaUsuario {
  +bigint usuario_id
  +varchar carrera_nombre
  +smallint cuatrimestre
  +boolean onboard
  +timestamptz actualizado_en
  --
  +actualizarCarrera(nombre)
  +actualizarCuatrimestre(n)
  +marcarOnboard(completado)
}

class PasswordResetToken {
  +bigint token_id
  +bigint usuario_id
  -bytes token_hash
  +timestamptz expira_en
  +timestamptz usado_en
  +timestamptz creado_en
  --
  +emitir(usuarioId)
  +validar(tokenPlano) bool
  +marcarUsado()
}

class Comunidad {
  +bigint comunidad_id
  +varchar nombre
  +varchar descripcion
  +boolean es_oficial
  +bigint creado_por
  +timestamptz creado_en
  +timestamptz actualizado_en
  --
  +crear(nombre, descripcion, esOficial)
  +editar(descripcion)
  +listarPublicaciones(filtros, orden)
  +agregarModerador(usuarioId)
  +removerModerador(usuarioId)
}

class ComunidadMiembro {
  +bigint comunidad_id
  +bigint usuario_id
  +char rol
  +timestamptz unido_en
  --
  +unir(usuarioId, comunidadId, rol)
  +salir(usuarioId, comunidadId)
  +cambiarRol(usuarioId, rol)
}

class Post {
  +bigint post_id
  +bigint comunidad_id
  +bigint autor_id
  +varchar titulo
  +text cuerpo
  +bigint mejor_comentario_id
  +char estado
  +timestamptz creado_en
  +timestamptz actualizado_en
  --
  +publicar(autorId, comunidadId, titulo, cuerpo)
  +editar(titulo, cuerpo)
  +cambiarEstado(estado)
  +setMejorComentario(comentarioId)
  +obtenerComentarios() list
}

class PostVoto {
  +bigint post_id
  +bigint usuario_id
  +smallint valor
  +timestamptz votado_en
  --
  +votar(usuarioId, postId, valor)
  +quitarVoto(usuarioId, postId)
}

class PostGuardado {
  +bigint post_id
  +bigint usuario_id
  +timestamptz guardado_en
  --
  +guardar(usuarioId, postId)
  +remover(usuarioId, postId)
}

class Comentario {
  +bigint comentario_id
  +bigint post_id
  +bigint autor_id
  +bigint comentario_padre_id
  +text cuerpo
  +timestamptz creado_en
  +timestamptz actualizado_en
  --
  +crear(autorId, postId, cuerpo, padreId)
  +editar(cuerpo)
  +eliminar()
}

class ComentarioVoto {
  +bigint comentario_id
  +bigint usuario_id
  +smallint valor
  +timestamptz votado_en
  --
  +votar(usuarioId, comentarioId, valor)
  +quitarVoto(usuarioId, comentarioId)
}

Usuario "1" --> "1" PreferenciaUsuario : tiene
Usuario "1" --> "0..*" ComunidadMiembro : participa
Comunidad "1" --> "0..*" ComunidadMiembro : miembros
Usuario "1" --> "0..*" Post : autor
Comunidad "1" --> "0..*" Post : contiene
Usuario "1" --> "0..*" Comentario : autor
Post "1" --> "0..*" Comentario : comentarios
Comentario "0..1" --> "0..*" Comentario : respuestas
Usuario "1" --> "0..*" PostGuardado : guarda
Post "1" --> "0..*" PostGuardado : guardado
Usuario "1" --> "0..*" PostVoto : vota
Post "1" --> "0..*" PostVoto : votos
Usuario "1" --> "0..*" ComentarioVoto : vota
Comentario "1" --> "0..*" ComentarioVoto : votos
PasswordResetToken "0..*" --> "1" Usuario : pertenece
```