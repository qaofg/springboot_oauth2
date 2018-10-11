# springboot_oauth2

Project Construction:
    springboot2.0 + security + oauth2

JDK version:
    jdk1.8

附件：
    1、解决错误：There is no PasswordEncoder mapped for the id “null”
        在SecurityConfiguration类中添加
        @Bean
        public static NoOpPasswordEncoder passwordEncoder() {
            return (NoOpPasswordEncoder) NoOpPasswordEncoder.getInstance();
        }

    2、解决错误：required a bean of type 'org.springframework.security.authentication.AuthenticationManager' that could not be found
        在SecurityConfiguration类中添加
        @Bean
        @Override
        public AuthenticationManager authenticationManagerBean() throws Exception {
            return super.authenticationManagerBean();
        }