# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: alemyre <alemyre@student.42lyon.fr>        +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2025/11/27 16:58:07 by alemyre           #+#    #+#              #
#    Updated: 2025/11/27 17:09:20 by alemyre          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME=	libftprintf.a

CC=		cc
CFLAGS=	-Wall -Wextra -Werror -MMD -MP
AR=		ar rcs

SRCS=	ft_printf.c
OBJS=	$(addprefix $(BUILD_DIR), $(SRCS:.c=.o))
DEPS=	$(OBJS:.o=.d)

BUILD_DIR = .build/

LIBFT=		libft
LIBFT_NAME=	libft.a
LIBFT_DIR=	libft/

all: $(NAME)

$(NAME): $(OBJS)
	make -C $(LIBFT)
	cp $(addprefix $(LIBFT_DIR), $(LIBFT_NAME))
	mv $(LIBFT_NAME) $(NAME)
	$(AR) $(NAME) $(OBJS)

-include $(DEPS) $(DEPS_B)

$(BUILD_DIR)%.o: %.c
	mkdir -p $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) $(OBJS_B) $(DEPS) $(DEPS_B)
	rm -f $(BONUS_N)
	rm -fd $(BUILD_DIR)

fclean: clean
	rm -f $(NAME)

re: fclean all

re_bonus: re bonus

.PHONY: all clean fclean re bonus re_bonus