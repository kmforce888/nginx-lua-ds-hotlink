# nginx-lua-ds-hotlink

        lua_package_path "/u/nginx/lua/ds_hotlink/?.lua;;";
        init_by_lua_file lua/ds_hotlink/init.lua;

        location = /get_key {
            allow 10.0.2.2;
            deny all;
            content_by_lua_file lua/ds_hotlink/get_key.lua;
        }
        
        access_by_lua_file lua/ds_hotlink/refer.lua;

        access_by_lua_file lua/ds_hotlink/accesskey.lua;
