SET(MARIADBCPP_PUBLIC_API   ${PROJECT_SOURCE_DIR}/include/conncpp.hpp)

SET(MARIADBCPP_PUBLIC_CLASSES ${PROJECT_SOURCE_DIR}/include/conncpp/Driver.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/DriverManager.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Connection.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Statement.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/PreparedStatement.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/ResultSet.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/DatabaseMetaData.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/ResultSetMetaData.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/CallableStatement.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Exception.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/SQLString.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Warning.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/ParameterMetaData.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Savepoint.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/Types.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/jdbccompat.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/buildconf.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/CArray.hpp
                            )

SET(MARIADBCPP_COMPAT_STUBS ${PROJECT_SOURCE_DIR}/include/conncpp/compat/Array.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/compat/Executor.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/compat/Object.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/compat/SQLType.hpp
                            ${PROJECT_SOURCE_DIR}/include/conncpp/compat/Struct.hpp
   )
IF(WIN32)
  SET(WIX_INCLUDES ${MARIADBCPP_PUBLIC_API} MARIADBCPP_PUBLIC_CLASSES {MARIADBCPP_COMPAT_STUBS} PARENT_SCOPE)
ENDIF()

INSTALL(FILES
   ${MARIADBCPP_PUBLIC_API}
   DESTINATION ${INSTALL_INCLUDEDIR}
   COMPONENT PublicAPI)
INSTALL(FILES
   ${MARIADBCPP_PUBLIC_CLASSES}
   DESTINATION ${INSTALL_INCLUDEDIR}/conncpp
   COMPONENT PublicAPI)
INSTALL(FILES
   ${MARIADBCPP_COMPAT_STUBS}
   DESTINATION ${INSTALL_INCLUDEDIR}/conncpp/compat
   COMPONENT PublicAPI)

